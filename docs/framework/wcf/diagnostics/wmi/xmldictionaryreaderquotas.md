---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f1c12a0a60397a84d4e9ff0241c4182b4511af5c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214885"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="91c3d-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="91c3d-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="91c3d-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="91c3d-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c3d-104">構文</span><span class="sxs-lookup"><span data-stu-id="91c3d-104">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="91c3d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="91c3d-105">Methods</span></span>  
 <span data-ttu-id="91c3d-106">XmlDictionaryReaderQuotas クラスで定義されるメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="91c3d-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="91c3d-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="91c3d-107">Properties</span></span>  
 <span data-ttu-id="91c3d-108">XmlDictionaryReaderQuotas クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="91c3d-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="91c3d-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="91c3d-109">MaxArrayLength</span></span>  
 <span data-ttu-id="91c3d-110">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="91c3d-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="91c3d-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="91c3d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91c3d-112">許される最大配列長。</span><span class="sxs-lookup"><span data-stu-id="91c3d-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="91c3d-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="91c3d-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="91c3d-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="91c3d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="91c3d-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="91c3d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91c3d-116">1 回の読み取りで返すことができる最大バイト数。</span><span class="sxs-lookup"><span data-stu-id="91c3d-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="91c3d-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="91c3d-117">MaxDepth</span></span>  
 <span data-ttu-id="91c3d-118">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="91c3d-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="91c3d-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="91c3d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91c3d-120">1 回の読み取りでの最大ネスト ノード深度。</span><span class="sxs-lookup"><span data-stu-id="91c3d-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="91c3d-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="91c3d-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="91c3d-122">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="91c3d-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="91c3d-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="91c3d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91c3d-124">テーブル名の最大文字数。</span><span class="sxs-lookup"><span data-stu-id="91c3d-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="91c3d-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="91c3d-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="91c3d-126">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="91c3d-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="91c3d-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="91c3d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="91c3d-128">XML 要素のコンテンツで許可される最大文字数。</span><span class="sxs-lookup"><span data-stu-id="91c3d-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91c3d-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="91c3d-129">Requirements</span></span>  
  
|<span data-ttu-id="91c3d-130">MOF</span><span class="sxs-lookup"><span data-stu-id="91c3d-130">MOF</span></span>|<span data-ttu-id="91c3d-131">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="91c3d-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="91c3d-132">名前空間</span><span class="sxs-lookup"><span data-stu-id="91c3d-132">Namespace</span></span>|<span data-ttu-id="91c3d-133">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="91c3d-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91c3d-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="91c3d-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
