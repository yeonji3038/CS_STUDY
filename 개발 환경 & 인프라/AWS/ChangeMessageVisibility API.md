# ChangeMessageVisibility API


> **ChangeMessageVisibility** API는 Amazon **SQS**(Simple Queue Service)에서
메시지를 처리할 때 사용되는 중요한 기능입니다.
메시지를 수신한 후, 처리 시간이 기본 가시성 타임아웃(Visibility
Timeout)보다 길어질 경우, 메시지가 다시 큐에 나타나 **중복 처리**되는
문제를 방지하기 위해 사용됩니다.

------------------------------------------------------------------------

## 동작 원리

1.  메시지가 **Consumer(예: EC2 인스턴스의 애플리케이션)** 에 의해
    수신되면,
    -   메시지는 큐에서 바로 삭제되지 않고, **Visibility Timeout** 동안
        다른 Consumer에게 보이지 않습니다.
2.  Consumer가 메시지를 처리한 후 `DeleteMessage` API를 호출해야 실제로
    큐에서 제거됩니다.
3.  만약 처리 시간이 **Visibility Timeout보다 길면**, 메시지가 큐에 다시
    나타나 다른 Consumer가 가져가서 **중복 처리**될 수 있습니다.
4.  이때 **ChangeMessageVisibility** API를 호출하여 **Visibility
    Timeout을 연장**하면, 메시지가 재등장하지 않고 안정적으로
    처리됩니다.

------------------------------------------------------------------------

## 주요 특징

-   기본 Visibility Timeout: 30초 (최대 12시간까지 설정 가능).
-   메시지 단위로 타임아웃을 연장할 수 있음.
-   메시지의 ReceiptHandle이 필요함.

------------------------------------------------------------------------

## 사용 예시 (AWS CLI)

``` bash
aws sqs change-message-visibility   --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/MyQueue   --receipt-handle AQEBz...example==   --visibility-timeout 120
```

-   `--queue-url`: 대상 큐의 URL
-   `--receipt-handle`: 메시지 수신 시 반환된 고유 식별자
-   `--visibility-timeout`: 새로 설정할 타임아웃 (초 단위)

------------------------------------------------------------------------

## 언제 사용해야 하나?

-   메시지 처리 시간이 예측 불가능하거나 긴 경우
-   DB에 저장, 외부 API 호출, 대용량 파일 처리 등 시간이 오래 걸리는
    작업 수행 시
-   중복 레코드 삽입, 중복 이벤트 처리와 같은 문제를 방지해야 할 때

------------------------------------------------------------------------

## 정리

-   **ChangeMessageVisibility API**는 메시지의 가시성 타임아웃을
    동적으로 조정하는 기능.
-   메시지가 처리되는 동안 다른 Consumer가 같은 메시지를 가져가지 않도록
    보장.
-   중복 처리 방지 및 안정적인 분산 메시지 처리 시스템 설계에 핵심적인
    역할을 함.
