# Задание 3. Технический радар

| Квадрант | Adopt (использовать) | Trial (пилотировать) | Assess (изучать) | Hold (выводить) |
|----------|-----------------------|-----------------------|------------------|-----------------|
| Хранилище данных | Data Lakehouse (Iceberg, Delta, Hudi), Object Storage | Feature Store (Feast, Tecton) | Data Mesh практики (domain data products) | SQL Server 2008 (DWH) |
| Обработка | Spark, Airflow | Flink (stream processing) | dbt (transformations) | PowerBuilder ETL-сценарии |
| Интеграции | REST/gRPC, Kafka, CDC | Event-driven architecture | GraphQL Federation для BI API | Apache Camel (старый ESB) |
| Говернанс | Data Catalog (Apache Atlas, Collibra, DataHub) | Data Quality frameworks (Great Expectations) | Data Contracts tooling | Кастомные Excel-реестры |
| Аналитика и BI | Power BI, Semantic Layer | Self-service portal prototype | Looker, Metriql exploration | Кастомные отчеты поверх DWH |
| Безопасность | IAM, RBAC, ABAC, KMS, DLP | Data Tokenization, De-identification | Attribute-based access control в BI | Локальная авторизация в приложениях |

--- 

# Роадмап

## Этап 1 (0–3 мес.)
Создание Data Catalog и Governance (пилот на финансовых данных)  
Запуск Lakehouse (bronze и silver зоны)  
Назначение владельцев доменов и data products  

- Результаты: базовая инфраструктура данных и контроль качества  
- Команды: Data Platform, Fintech domain team  
- Ресурсы: облачное хранилище, лицензия Data Catalog  

## Этап 2 (3–6 мес.)
Развертывание Gold-зоны Lakehouse и связка с BI Semantic Layer  
Запуск self-service BI (прототип для финтеха и клиник)  
Внедрение Data Quality (Great Expectations)  

- Результаты: первые отчеты через витрину  
- Команды: BI team, Healthcare domain team  
- Ресурсы: compute-кластер, BI лицензии  

## Этап 3 (6–9 мес.)
Внедрение стриминга через Kafka и Flink для данных клиник и устройств  
Подключение AI domain (медизображения, фичи)  
Начало вывода отчетов из Legacy DWH  

- Результаты: real-time данные для ИИ и клиник  
- Команды: AI/ML team, Devices team  
- Ресурсы: GPU и ML инфраструктура, Kafka cluster  

## Этап 4 (9–12 мес.)
Развертывание Data Mesh с независимыми витринами доменов  
Добавление Feature Store  
Фазовый отказ от SQL Server 2008 и Apache Camel  

- Результаты: независимость доменов, готовность к масштабированию новых бизнесов  
- Команды: все доменные команды, Data Platform  
- Ресурсы: бюджеты на миграцию, обучение команд  

---

# Обоснование изменений

1. Data Lakehouse объединяет подход DWH для структурированных данных и хранение для ИИ. Решает проблемы производительности и гибкости.  
2. Data Mesh отражает организационное разделение по бизнесам. Позволяет независимое развитие и снижает нагрузку на центральный DWH.  
3. Data Catalog и Governance обеспечивают прозрачность, поиск, lineage и контроль доступа. Повышают доверие бизнеса к данным.  
4. Semantic Layer и Self-Service BI ускоряют аналитику и позволяют бизнес-пользователям строить отчеты без участия ИТ.  
5. Stream Processing (Kafka, Flink) обеспечивает поддержку real-time сценариев для клиник, устройств и скоринга кредитов.  
6. Feature Store необходим для развития ИИ-направления и повторного использования ML-фич.  
7. Вывод из эксплуатации Legacy DWH и Camel снижает затраты на поддержку и устраняет зависимость от устаревших технологий.
