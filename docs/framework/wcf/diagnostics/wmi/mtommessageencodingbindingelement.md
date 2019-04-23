---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: aed65311d2b36a5dc764511de04e34c4bfb69d7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59978173"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="858bf-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="858bf-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="858bf-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="858bf-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="858bf-104">構文</span><span class="sxs-lookup"><span data-stu-id="858bf-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="858bf-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="858bf-105">Methods</span></span>  
 <span data-ttu-id="858bf-106">MtomMessageEncodingBindingElement クラスで定義されているメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="858bf-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="858bf-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="858bf-107">Properties</span></span>  
 <span data-ttu-id="858bf-108">MtomMessageEncodingBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="858bf-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="858bf-109">エンコード</span><span class="sxs-lookup"><span data-stu-id="858bf-109">Encoding</span></span>  
 <span data-ttu-id="858bf-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="858bf-110">Data type: string</span></span>  
  
 <span data-ttu-id="858bf-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="858bf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="858bf-112">バインディングでメッセージの送信に使用される文字セット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="858bf-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="858bf-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="858bf-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="858bf-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="858bf-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="858bf-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="858bf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="858bf-116">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="858bf-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="858bf-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="858bf-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="858bf-118">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="858bf-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="858bf-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="858bf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="858bf-120">新しいライターを割り当てずに同時に送信可能なメッセージの数を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="858bf-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="858bf-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="858bf-121">ReaderQuotas</span></span>  
 <span data-ttu-id="858bf-122">データの種類:XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="858bf-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="858bf-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="858bf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="858bf-124">リーダのクォータ。</span><span class="sxs-lookup"><span data-stu-id="858bf-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="858bf-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="858bf-125">Requirements</span></span>  
  
|<span data-ttu-id="858bf-126">MOF</span><span class="sxs-lookup"><span data-stu-id="858bf-126">MOF</span></span>|<span data-ttu-id="858bf-127">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="858bf-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="858bf-128">名前空間</span><span class="sxs-lookup"><span data-stu-id="858bf-128">Namespace</span></span>|<span data-ttu-id="858bf-129">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="858bf-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="858bf-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="858bf-130">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
