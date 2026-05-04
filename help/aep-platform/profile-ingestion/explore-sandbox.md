---
title: 存取及探索AEP沙箱
description: 瞭解如何存取及探索Experience Platform沙箱。
exl-id: 62c21615-4b03-4900-a1ad-8f809c836491
TQID: https://experienceleague.adobe.com/A5sl-xNZBPjIKn6HO1iwM78IaQWQs4yBgbw9wwpMrGw
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
subfeature_v2: id: b75843fa-0a67-4a44-a6b1-cc627b0481dcid: fef08361-6ac5-460c-93fe-d063e40b6a49
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 6698ae880d1ad13a9387cb1ba66b9ba152d1d407
workflow-type: tm+mt
source-wordcount: 772
ht-degree: 1%

---

# 存取及探索AEP沙箱

本文涵蓋下列內容：

* 現有Adobe Exchange合作夥伴沙箱組織與共用AEP沙箱之間的差異。
* 正在請求存取AEP共用沙箱。
* 正在接收加入AEP共用沙箱的電子郵件邀請。
* 在[!DNL Admin Console]中邀請新使用者。
* 導覽AEP UI。

如需AEP中沙箱技術的一般概觀，請參閱此[文章](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html)。

## 共用的AEP沙箱

Exchange合作夥伴可透過其自己的Adobe [!DNL Experience Cloud]組織（非共用），存取各種Adobe [!DNL Experience Cloud]產品（非AEP產品，例如[!DNL Analytics]、[!DNL Target]、Platform標籤等）。 合作夥伴被授予系統管理員對其自身組織的存取權以管理使用者和其他許可權。 Adobe [!DNL Experience Platform] (AEP)的處理方式與其他Adobe沙箱不同。 主要差異如下：

* 無法透過主要Adobe [!DNL Experience Cloud]沙箱組織的合作夥伴存取AEP。
* 若要存取AEP，需透過共用的Adobe Exchange組織。
* 許多其他Adobe Exchange合作夥伴公司也使用相同的組織存取AEP
   * 透過AEP沙箱功能，其他合作夥伴將無法檢視或修改此共用組織內的資料和活動；每個合作夥伴都可以存取共用組織內的不同沙箱。
* 此共用組織中的管理許可權非常有限。
* 獲得在AEP上存取沙箱的許可權後，合作夥伴將在UI的右上角在Org Switcher上看到兩個組織，同時在Admin Console或Experience Cloud首頁中。 不過，登入AEP時，應該只會顯示共用的組織。

## 請求共用AEP沙箱的存取權

送出[支援要求](https://adobeexchangeec.zendesk.com/hc/en-us/requests/new)，並提供下列資訊：

* 電子郵件地址
* 主旨： AEP沙箱要求
* 產品：一般布建/沙箱
* 票證型別：方案支援 — Exchange方案/布建要求問題
* 說明：提供需要使用AEP沙箱的整合使用案例的簡短說明
* 也請務必提供應新增至AEP沙箱的所有使用者名稱和電子郵件。 提出請求後可新增其他使用者，但使用者必須由Adobe透過其他票證新增（請參閱下文）。

## 接收電子郵件邀請

要求AEP沙箱的主要連絡人將會收到自動電子郵件，邀請他們「開始」使用Adobe [!DNL Experience Platform]。 主要連絡人也會有一些管理許可權，詳見下一節。

不要在電子郵件中選取[開始使用]按鈕，請直接導覽至與邀請函中的電子郵件地址相關聯的Adobe ID登入`https://platform.adobe.com.`，或建立一個（如果未與Adobe ID相關聯）。

## 邀請其他使用者

送出[支援要求](https://adobeexchangeec.zendesk.com/hc/en-us/requests/new)，並提供下列資訊：

* 要求者電子郵件地址
* 主旨： AEP Sandbox — 新增管理員/使用者
* 產品：一般布建/沙箱
* 票證型別：方案支援 — Exchange方案/布建要求問題
* 說明：要新增的使用者清單（名稱和電子郵件）

## 導覽AEP UI

觀看AEP UI [簡介影片](https://docs.adobe.com/content/help/en/platform-learn/tutorials/intro-to-platform/interface-tour.html)

AEP UI中有12個主要區域可透過左側面板瀏覽。 不過，此類整合最重要的區段是結構描述、資料集和設定檔。

* 首頁 — 登陸畫面

   * 建議一些快速入門活動
   * 提供學習內容的一些連結
   * 提供某些主要AEP物件的儀表板檢視，例如結構描述、資料集和設定檔

* 工作流程 — 將資料引進AEP的常用工作流程啟動
* 連線/來源 — 管理傳入AEP的資料來源
* 連線/目的地 — 管理連線，以將資料傳送至外部系統
* 設定檔 — 檢視和管理個別客戶設定檔
* 區段 — 瀏覽、建立和修改客戶區段
* 身分 — 瀏覽、建立和修改身分名稱空間；這些是用來唯一識別客戶的主要ID型別
* 模型（資料科學） — 參與資料科學活動，包括使用內嵌Jupyter Notebooks環境
* 服務（資料科學） — 以服務形式發佈資料科學配方
* 結構描述 — 瀏覽、建立和修改結構描述；這些是用於保持資料條理化的詳細資料定義
* 資料集 — 瀏覽、建立及管理資料集；資料集由結構描述定義，且資料位於AEP內
* 查詢 — 瀏覽、建立、修改和使用查詢存放庫，以從DataSets內的資料獲得見解
* 監視 — 檢視移入和移出AEP的所有資料狀態，包括批次和串流
