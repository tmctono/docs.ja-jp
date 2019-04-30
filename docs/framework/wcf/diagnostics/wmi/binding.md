---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: a040cc6e12833d2c737eb14c591300e5873ddce7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964075"
---
# <a name="binding"></a><span data-ttu-id="7a0b9-102">バインディング</span><span class="sxs-lookup"><span data-stu-id="7a0b9-102">Binding</span></span>
<span data-ttu-id="7a0b9-103">wmi バインディング</span><span class="sxs-lookup"><span data-stu-id="7a0b9-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a0b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="7a0b9-104">Syntax</span></span>  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7a0b9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7a0b9-105">Methods</span></span>  
 <span data-ttu-id="7a0b9-106">Binding クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7a0b9-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7a0b9-107">Properties</span></span>  
 <span data-ttu-id="7a0b9-108">Binding クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="7a0b9-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="7a0b9-109">BindingElements</span></span>  
 <span data-ttu-id="7a0b9-110">データの種類:BindingElement 配列</span><span class="sxs-lookup"><span data-stu-id="7a0b9-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="7a0b9-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="7a0b9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a0b9-112">バインディングによって実装されるバインド要素のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="7a0b9-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="7a0b9-113">CloseTimeout</span></span>  
 <span data-ttu-id="7a0b9-114">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="7a0b9-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="7a0b9-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="7a0b9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a0b9-116">クローズ操作が完了するまで待機する時間です。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="7a0b9-117">名前</span><span class="sxs-lookup"><span data-stu-id="7a0b9-117">Name</span></span>  
 <span data-ttu-id="7a0b9-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="7a0b9-118">Data type: string</span></span>  
  
 <span data-ttu-id="7a0b9-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="7a0b9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a0b9-120">バインディングの名前。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="7a0b9-121">名前空間</span><span class="sxs-lookup"><span data-stu-id="7a0b9-121">Namespace</span></span>  
 <span data-ttu-id="7a0b9-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="7a0b9-122">Data type: string</span></span>  
  
 <span data-ttu-id="7a0b9-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="7a0b9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a0b9-124">バインディングの XML 名前空間。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="7a0b9-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="7a0b9-125">OpenTimeout</span></span>  
 <span data-ttu-id="7a0b9-126">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="7a0b9-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="7a0b9-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="7a0b9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a0b9-128">オープン操作が完了するまで待機する時間です。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="7a0b9-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="7a0b9-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="7a0b9-130">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="7a0b9-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="7a0b9-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="7a0b9-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a0b9-132">受信操作が完了するまで待機する時間です。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="7a0b9-133">Scheme</span><span class="sxs-lookup"><span data-stu-id="7a0b9-133">Scheme</span></span>  
 <span data-ttu-id="7a0b9-134">データ型: string</span><span class="sxs-lookup"><span data-stu-id="7a0b9-134">Data type: string</span></span>  
  
 <span data-ttu-id="7a0b9-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="7a0b9-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a0b9-136">このバインディングに組み込まれているチャネルおよびリスナー ファクトリによって使用される URI トランスポート スキームです。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="7a0b9-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="7a0b9-137">SendTimeout</span></span>  
 <span data-ttu-id="7a0b9-138">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="7a0b9-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="7a0b9-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="7a0b9-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a0b9-140">送信操作が完了するまで待機する時間です。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a0b9-141">必要条件</span><span class="sxs-lookup"><span data-stu-id="7a0b9-141">Requirements</span></span>  
  
|<span data-ttu-id="7a0b9-142">MOF</span><span class="sxs-lookup"><span data-stu-id="7a0b9-142">MOF</span></span>|<span data-ttu-id="7a0b9-143">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="7a0b9-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7a0b9-144">名前空間</span><span class="sxs-lookup"><span data-stu-id="7a0b9-144">Namespace</span></span>|<span data-ttu-id="7a0b9-145">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="7a0b9-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a0b9-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a0b9-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
