---
title: カスタム追跡レコード
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 986f0350c24414d0ff960474445adf6ac3f39734
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802623"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="ad6ea-102">カスタム追跡レコード</span><span class="sxs-lookup"><span data-stu-id="ad6ea-102">Custom Tracking Records</span></span>

<span data-ttu-id="ad6ea-103">このトピックではカスタム追跡レコードを作成し、出力されたデータをレコードと一緒に読み込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad6ea-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>

## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="ad6ea-104">カスタム追跡レコードの出力</span><span class="sxs-lookup"><span data-stu-id="ad6ea-104">Emitting Custom Tracking Records</span></span>

<span data-ttu-id="ad6ea-105">次の例に示すように、カスタム追跡レコードはコード アクティビティから出力できます。</span><span class="sxs-lookup"><span data-stu-id="ad6ea-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

<span data-ttu-id="ad6ea-106"><xref:System.Activities.Tracking.CustomTrackingRecord> 上で <xref:System.Activities.NativeActivityContext.Track%2A> メソッドを呼び出すことで、`ActivityContext` をコード アクティビティに出力できます。</span><span class="sxs-lookup"><span data-stu-id="ad6ea-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActivityContext`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad6ea-107">参照</span><span class="sxs-lookup"><span data-stu-id="ad6ea-107">See also</span></span>

- <span data-ttu-id="ad6ea-108">[Windows Server App Fabric の監視](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ad6ea-108">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="ad6ea-109">[App Fabric を使用したアプリケーションの監視](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ad6ea-109">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
