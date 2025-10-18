| Название                      | Тип            | Компоненты                                                     | Предусловия                                                |
|-------------------------------|----------------|----------------------------------------------------------------|------------------------------------------------------------|
| Happy Path - Успешный платеж  | E2E            | PaymentOrchestrator, Payment Service, FraudCheck, Notification | Баланс клиента > суммы платежа, все проверки APPROVED      |
| Автоматический отказ по фроду | Интеграционный | PaymentOrchestrator, FraudCheck, Refund Service                | Баланс клиента > суммы платежа, FraudCheck = REJECTED      |
| Ручная проверка с разрешением | E2E            | PaymentOrchestrator, FraudCheck, UserTask, Notification        | Баланс клиента > суммы платежа, FraudCheck = MANUAL_REVIEW |
| Таймаут ручной проверки       | Интеграционный | PaymentOrchestrator, FraudCheck, UserTask                      | Баланс клиента > суммы платежа, FraudCheck = MANUAL_REVIEW |
| Ошибка списания средств       | Интеграционный | PaymentOrchestrator, Payment Service                           | Баланс клиента < суммы платежа                             |

