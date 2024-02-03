---
title: 即時匯入
description: 瞭解如何即時將資料匯入AEP。
exl-id: 0b6215a9-1160-49ae-8aa5-302b47357200
source-git-commit: fe7519c35fb9155ce54cad85941c887f15881a38
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# 將資料串流至AEP

Adobe [!DNL Experience Platform] 可讓設定檔和體驗事件串流化，並可近乎即時使用。 所有透過串流傳送至AEP的資料都會保留在資料湖中。 您可以透過API或使用Adobe Launch將資料串流至現有資料集或全新的資料集。

本文章將涵蓋下列內容：

* 串流至XDM個人設定檔
* 串流至XDM ExperienceEvent
* 使用AEP Launch擴充功能進行串流

此 [Postman集合](https://github.com/Adobe-Marketing-Cloud/exchange-aep-profile-integration-postman) 整篇文章都會使用相關的呼叫次數來參照。 有關安裝和使用Postman集合的詳細資訊，請參閱Github [讀我檔案](https://github.com/Adobe-Marketing-Cloud/exchange-aep-profile-integration-postman/blob/master/README.md) 頁面。 也有範例資料集 [忠誠度](https://github.com/Adobe-Marketing-Cloud/exchange-aep-profile-integration-postman/blob/master/AEP%20loyalty%20events.json) 和 [設定檔](https://github.com/Adobe-Marketing-Cloud/exchange-aep-profile-integration-postman/blob/master/AEP%20loyalty%20profiles.json) 資料。

## 先決條件

* [驗證平台](https://docs.adobe.com/content/help/en/experience-platform/tutorials/authentication.html).
* 從上方連結的驗證教學課程收集所需標題的值。

## 建立串流連線

若要串流至AEP，您必須先建立串流連線。 串流連線包含串流資料來源之類的屬性，以及您是否要在屬於 [!DNL Experience Data Model] (XDM)結構描述。 建立串流連線後，您會獲得唯一的URL，可用來將資料串流至AEP。

前往 [此處](https://docs.adobe.com/content/help/en/experience-platform/ingestion/tutorials/create-streaming-connection.html) 有關如何透過API建立串流連線的說明，或 [此處](https://docs.adobe.com/content/help/en/experience-platform/ingestion/tutorials/create-streaming-connection-ui.html) 以取得有關如何透過UI建立串流連線的指示。

```json
curl -X POST https://platform.adobe.io/data/foundation/flowservice/connections \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'Content-Type: application/json' \
 -H 'x-gw-ims-org-id: {IMS_ORG}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}' \
 -d '{
     "name": "Sample name",
     "providerId": "521eee4d-8cbe-4906-bb48-fb6bd4450033",
     "description": "Sample description",
     "connectionSpec": {
         "id": "bc7b00d6-623a-4dfc-9fdb-f1240aeadaeb",
         "version": "1.0"
     },
     "auth": {
         "specName": "Streaming Connection",
         "params": {
             "sourceId": "Sample connection",
             "dataType": "xdm",
             "name": "Sample connection"
         }
     }
 }
```

回應：

```json
 {
    "id": "77a05521-91d6-451c-a055-2191d6851c34",
    "etag": "\"a500e689-0000-0200-0000-5e31df730000\""
}
```

請務必儲存上述回應中提供的ID，以供日後的串流擷取呼叫使用(Postman集合會將此專案儲存在CONNECTION_ID環境變數中)。

## 將設定檔資料串流至AEP

針對本節，使用Postman呼叫資料夾： 3：即時匯入，3a：設定檔資料的即時匯入。

詳細說明的JSON請求以及串流設定檔資料的回應會記錄下來 [此處](https://docs.adobe.com/content/help/en/experience-platform/ingestion/tutorials/streaming-record-data.html).

步驟：

1. 建立XDM個別設定檔結構描述
1. 設定XDM個人資料的主要身分描述項（主索引鍵）
1. 為XDM個別設定檔記錄建立資料集
1. 呼叫串流擷取API以建立XDM個別設定檔記錄
1. 擷取新建立的設定檔

## 將體驗事件串流至AEP

對於本節，使用Postman呼叫資料夾： 3：即時匯入，3b：設定檔資料的即時匯入。

包含串流體驗資料回應的詳細JSON請求會記錄下來 [此處](https://docs.adobe.com/content/help/en/experience-platform/ingestion/tutorials/streaming-time-series-data.html).

步驟：

1. 建立XDM ExperienceEvent結構描述
1. 設定XDM ExperienceEvent的主要身分描述項（主索引鍵）
1. 建立XDM ExperienceEvents的資料集
1. 呼叫串流擷取API以建立XDM ExperienceEvent
1. 擷取新建立的事件

## 使用Experience Platform標籤串流至AEP

Adobe [!DNL Experience Platform] Launch擴充功能提供透過Launch串流至AEP的方式。 若要深入瞭解，請參閱 [本指南](https://docs.adobe.com/content/help/zh-Hant/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html).

## 參考文章

* [資料擷取API](https://www.adobe.io/apis/experienceplatform/home/api-reference.html#/acpdr/swagger-specs)
* [串流擷取概觀](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)
* [串流擷取開發人員指南](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)
* [使用AEP Launch擴充功能](https://docs.adobe.com/content/help/zh-Hant/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html)
