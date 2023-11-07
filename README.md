# Моя работа
## Achievement Service - работа с достижениями
[Общий интерфейс](https://github.com/Dlakares/achievement_service/blob/medusa-master/src/main/java/faang/school/achievement/service/handler/EventHandler.java), [абстрактный класс](https://github.com/Dlakares/achievement_service/blob/medusa-master/src/main/java/faang/school/achievement/service/handler/invitation/StageInvitationAchievement.java) для достижений определённого типа и [обработчик достижения](https://github.com/Dlakares/achievement_service/blob/medusa-master/src/main/java/faang/school/achievement/service/handler/invitation/OrganizerAchievementHandler.java) работают в совокупности и предполагают просто добавление новых достижений и обновление функционала
## Analytics Service

[Сервис](https://github.com/Dlakares/analytics_service/blob/medusa-master/src/main/java/faang/school/analytics/service/AnalyticsEventService.java) выполняет работу по сохранению аналитики в общем виде.

[Слушатель](https://github.com/Dlakares/analytics_service/blob/medusa-master/src/main/java/faang/school/analytics/messaging/FundRaisedEventListener.java) ивентов ловит событие и дальше [хенлдер](https://github.com/Dlakares/analytics_service/blob/medusa-master/src/main/java/faang/school/analytics/service/FundRaisedEventHandler.java) который сохраняет сущность в БД.

## Notification Service - обработка и отправление нотификаций
[Абстрактный дженерик класс](https://github.com/Dlakares/notification_service/blob/medusa-master/src/main/java/faang/school/notificationservice/notification/NotificationSender.java) который строит сообщение с помощью [Message Builder](https://github.com/Dlakares/notification_service/blob/medusa-master/src/main/java/faang/school/notificationservice/service/SkillOfferedMessageBuilder.java) (в моём случае под мой тип нотификации), после чего выбирает предпочитаемый вид контакта пользователя и отправляет этим способом нотификацию

## Payment Service - работа с оплатой
Участвовал в разработке оплаты через DMS.
[Законфигурировал](https://github.com/Dlakares/payment_service/blob/medusa-master/src/main/java/faang/school/paymentservice/config/RedisConfig.java) работу с редисом и спроектировал [таблицу](https://github.com/Dlakares/payment_service/blob/medusa-master/src/main/resources/db/changelog/changeset/V001__payment-service_payment-table.sql)

[Контроллер](https://github.com/Dlakares/payment_service/blob/medusa-master/src/main/java/faang/school/paymentservice/controller/PaymentController.java) поддерживает - создание, отмену, планирование и проведение платежа

[Планироващик](https://github.com/Dlakares/payment_service/blob/medusa-master/src/main/java/faang/school/paymentservice/scheduling/payment/PaymentScheduler.java) - создаёт запланирование платежи

[Сервис](https://github.com/Dlakares/payment_service/blob/medusa-master/src/main/java/faang/school/paymentservice/service/payment/PaymentService.java) выполняет все действия описанные в контроллере


## Account Service - работа с балансами пользователей
Спроектировал таблицы [баланса](https://github.com/Dlakares/account_service/blob/medusa-master/src/main/resources/db/changelog/changeset/V004__account-service_balance-table.sql) и [истории баланса](https://github.com/Dlakares/account_service/blob/medusa-master/src/main/resources/db/changelog/changeset/V005__account-service_balances_history-table.sql)

[Контроллер](https://github.com/Dlakares/account_service/blob/medusa-master/src/main/java/faang/school/accountservice/controller/BalanceController.java) - создание, обновление и получение [баланса](https://github.com/Dlakares/account_service/blob/medusa-master/src/main/java/faang/school/accountservice/model/Balance.java)

[Сущность истории баланса](https://github.com/Dlakares/account_service/blob/medusa-master/src/main/java/faang/school/accountservice/model/BalanceHistory.java)

[Сервисный класс баланса](https://github.com/Dlakares/account_service/blob/medusa-master/src/main/java/faang/school/accountservice/service/balance/BalanceService.java)

## Остальные сервисы
В них сделана минимальная работа, так что решаю не тратить ваше время на CRUD операции, хоть и с добавлением некоторой логики
