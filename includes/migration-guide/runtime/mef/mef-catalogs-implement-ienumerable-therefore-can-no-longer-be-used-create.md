---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235574"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="9f7fa-101">MEF カタログは IEnumerable を実装するため、シリアライザーの作成には使用できなくなった</span><span class="sxs-lookup"><span data-stu-id="9f7fa-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9f7fa-102">説明</span><span class="sxs-lookup"><span data-stu-id="9f7fa-102">Details</span></span>|<span data-ttu-id="9f7fa-103">.NET Framework 4.5 以降では、MEF カタログは IEnumerable を実装するため、シリアライザー (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> オブジェクト) の作成には使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9f7fa-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> object).</span></span> <span data-ttu-id="9f7fa-104">MEF カタログをシリアル化しようとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="9f7fa-104">Trying to serialize a MEF catalog throws an exception.</span></span>|
|<span data-ttu-id="9f7fa-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="9f7fa-105">Suggestion</span></span>|<span data-ttu-id="9f7fa-106">シリアライザーの作成に MEF を使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9f7fa-106">Can no longer use MEF to create a serializer</span></span>|
|<span data-ttu-id="9f7fa-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="9f7fa-107">Scope</span></span>|<span data-ttu-id="9f7fa-108">Major</span><span class="sxs-lookup"><span data-stu-id="9f7fa-108">Major</span></span>|
|<span data-ttu-id="9f7fa-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="9f7fa-109">Version</span></span>|<span data-ttu-id="9f7fa-110">4.5</span><span class="sxs-lookup"><span data-stu-id="9f7fa-110">4.5</span></span>|
|<span data-ttu-id="9f7fa-111">型</span><span class="sxs-lookup"><span data-stu-id="9f7fa-111">Type</span></span>|<span data-ttu-id="9f7fa-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="9f7fa-112">Runtime</span></span>|
