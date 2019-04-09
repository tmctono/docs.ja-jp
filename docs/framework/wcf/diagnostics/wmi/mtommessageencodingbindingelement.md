---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: aed65311d2b36a5dc764511de04e34c4bfb69d7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140479"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="1676a-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="1676a-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="1676a-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="1676a-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1676a-104">構文</span><span class="sxs-lookup"><span data-stu-id="1676a-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1676a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1676a-105">Methods</span></span>  
 <span data-ttu-id="1676a-106">MtomMessageEncodingBindingElement クラスで定義されているメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="1676a-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1676a-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1676a-107">Properties</span></span>  
 <span data-ttu-id="1676a-108">MtomMessageEncodingBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="1676a-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="1676a-109">エンコード</span><span class="sxs-lookup"><span data-stu-id="1676a-109">Encoding</span></span>  
 <span data-ttu-id="1676a-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1676a-110">Data type: string</span></span>  
  
 <span data-ttu-id="1676a-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1676a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1676a-112">バインディングでメッセージの送信に使用される文字セット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="1676a-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="1676a-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="1676a-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="1676a-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="1676a-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="1676a-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1676a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1676a-116">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="1676a-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="1676a-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="1676a-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="1676a-118">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="1676a-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="1676a-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1676a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1676a-120">新しいライターを割り当てずに同時に送信可能なメッセージの数を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="1676a-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="1676a-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="1676a-121">ReaderQuotas</span></span>  
 <span data-ttu-id="1676a-122">データの種類:XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="1676a-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="1676a-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1676a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1676a-124">リーダのクォータ。</span><span class="sxs-lookup"><span data-stu-id="1676a-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1676a-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="1676a-125">Requirements</span></span>  
  
|<span data-ttu-id="1676a-126">MOF</span><span class="sxs-lookup"><span data-stu-id="1676a-126">MOF</span></span>|<span data-ttu-id="1676a-127">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="1676a-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1676a-128">名前空間</span><span class="sxs-lookup"><span data-stu-id="1676a-128">Namespace</span></span>|<span data-ttu-id="1676a-129">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="1676a-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1676a-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="1676a-130">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
