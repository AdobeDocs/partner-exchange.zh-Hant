---
title: '[!DNL Platform]設定檔擷取與存取整合指南概觀'
description: 瞭解 [!DNL Experience Platform] 設定檔擷取與存取的整合。
exl-id: a593511c-dd4c-4437-af73-f44d795cacb8
source-git-commit: fe7519c35fb9155ce54cad85941c887f15881a38
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# 整合指南： [!DNL Experience Platform]設定檔擷取與存取

合作夥伴應使用此整合指南，協助他們使用Adobe[!DNL Experience Platform] (AEP)建置輸入和輸出功能。 有API可用於批次擷取、串流擷取和統一設定檔存取（輸出）。

為了協助開發，Adobe Exchange團隊已建立[Postman集合](https://github.com/Adobe-Marketing-Cloud/exchange-aep-profile-integration-postman)。 整份整合指南都會參考此Postman集合。

有關安裝和使用Postman集合的詳細資訊，請參閱Github [README](https://github.com/Adobe-Marketing-Cloud/exchange-aep-profile-integration-postman/blob/master/README.md)頁面。 還有[忠誠度](https://github.com/Adobe-Marketing-Cloud/exchange-aep-profile-integration-postman/blob/master/AEP%20loyalty%20events.json)和[個人資料](https://github.com/Adobe-Marketing-Cloud/exchange-aep-profile-integration-postman/blob/master/AEP%20loyalty%20profiles.json)資料的範例資料集。

## 整合使用案例範例：互動式語音回應系統

對於整合經銷商而言，[!DNL Experience Platform] API提供平台的所有功能，這些功能在整個使用者介面中提供，但現在可建立客戶工作流程及自動化資料流程。 身為整合者，您可以定期檢查資料集的狀態、設定新的資料擷取程式，並將您自己的對象啟用解決方案與整合式設定檔整合。

以互動式語音回應(IVR)系統和客服中心管理軟體為例。 供應商可以使用[!DNL Experience Platform] API來擷取體驗資料湖中客戶客服中心活動的歷史資訊。 如果資料是以XDM `ExperienceEvent`結構描述（表示客戶互動的結構描述）擷取，這些互動可以直接擷取到統一設定檔服務，而不會產生摩擦。 在此情況下，`callerId`會用作客戶的識別碼。 Identity Service會負責身分解析，並協助Unified Profile Service將任何最近與客服中心互動的資料點新增至客戶設定檔。

下次客戶致電客服中心時，IVR會先接聽客戶。 若要個人化訊息並傳送專為來電者量身打造的優惠方案，IVR系統需要瞭解更多有關來電者的資訊。 這是API與統一設定檔整合的功能。 IVR後端可以連絡整合設定檔服務以進行點查詢。 然後，請查閱只適用於客服中心互動的設定檔屬性，或完整客戶設定檔，此設定檔也包含其他接觸點上的互動屬性。 透過結合來自多個資料來源的資料、使用身分解析和Unified Profile，呼叫中心和IVR提供者可以提供量身打造的客戶體驗，並受Adobe[!DNL Experience Platform]的支援。」

## 一般資源

* AEP [產品檔案](https://docs.adobe.com/content/help/zh-Hant/experience-platform/landing/documentation/overview.html)。
* AEP [擴充性](https://www.adobe.com/insights/experience-platform-api-extensibility.html)。

## 有問題或意見反應？

請透過[支援管道](https://adobeexchangeec.zendesk.com/hc/en-us/requests/new)提交所有問題和意見
