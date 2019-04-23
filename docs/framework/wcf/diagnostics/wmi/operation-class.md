---
title: Operation class
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 9696a7f026e54afacb5ccbfa8703a2ba617a9f3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973201"
---
# <a name="operation-class"></a><span data-ttu-id="87a0f-102">Operation class</span><span class="sxs-lookup"><span data-stu-id="87a0f-102">Operation class</span></span>
<span data-ttu-id="87a0f-103">操作</span><span class="sxs-lookup"><span data-stu-id="87a0f-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a0f-104">構文</span><span class="sxs-lookup"><span data-stu-id="87a0f-104">Syntax</span></span>  
  
```csharp
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="87a0f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="87a0f-105">Methods</span></span>  
 <span data-ttu-id="87a0f-106">Operation クラスで定義されているメソッドはありせん。</span><span class="sxs-lookup"><span data-stu-id="87a0f-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="87a0f-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="87a0f-107">Properties</span></span>  
 <span data-ttu-id="87a0f-108">Operation クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="87a0f-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="87a0f-109">アクション</span><span class="sxs-lookup"><span data-stu-id="87a0f-109">Action</span></span>  
 <span data-ttu-id="87a0f-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="87a0f-110">Data type: string</span></span>  
  
 <span data-ttu-id="87a0f-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-112">要求メッセージの WS-Addressing 操作。</span><span class="sxs-lookup"><span data-stu-id="87a0f-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="87a0f-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="87a0f-113">AsyncPattern</span></span>  
 <span data-ttu-id="87a0f-114">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="87a0f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="87a0f-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-116">非同期的を使用して、操作を実装することを示します、 `Begin`[開く/閉じる山かっこ] と`End`サービス コントラクトで [開く/閉じる山かっこ] メソッドのペア。</span><span class="sxs-lookup"><span data-stu-id="87a0f-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="87a0f-117">ビヘイビアー</span><span class="sxs-lookup"><span data-stu-id="87a0f-117">Behaviors</span></span>  
 <span data-ttu-id="87a0f-118">データの種類:動作の配列</span><span class="sxs-lookup"><span data-stu-id="87a0f-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="87a0f-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-120">この操作に関連付けられている動作。</span><span class="sxs-lookup"><span data-stu-id="87a0f-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="87a0f-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="87a0f-121">IsCallback</span></span>  
 <span data-ttu-id="87a0f-122">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="87a0f-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="87a0f-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-124">この操作がコールバック操作の場合、True。</span><span class="sxs-lookup"><span data-stu-id="87a0f-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="87a0f-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="87a0f-125">IsInitiating</span></span>  
 <span data-ttu-id="87a0f-126">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="87a0f-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="87a0f-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-128">メソッドが、サーバーでセッションを開始できる操作を実装するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="87a0f-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="87a0f-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="87a0f-129">IsOneWay</span></span>  
 <span data-ttu-id="87a0f-130">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="87a0f-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="87a0f-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-132">操作が応答メッセージを返すかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="87a0f-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="87a0f-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="87a0f-133">IsTerminating</span></span>  
 <span data-ttu-id="87a0f-134">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="87a0f-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="87a0f-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-136">操作が応答メッセージを返すかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="87a0f-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="87a0f-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="87a0f-137">MethodSignature</span></span>  
 <span data-ttu-id="87a0f-138">データ型: string</span><span class="sxs-lookup"><span data-stu-id="87a0f-138">Data type: string</span></span>  
  
 <span data-ttu-id="87a0f-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-140">操作のメソッド署名。</span><span class="sxs-lookup"><span data-stu-id="87a0f-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="87a0f-141">名前</span><span class="sxs-lookup"><span data-stu-id="87a0f-141">Name</span></span>  
 <span data-ttu-id="87a0f-142">データ型: string</span><span class="sxs-lookup"><span data-stu-id="87a0f-142">Data type: string</span></span>  
  
 <span data-ttu-id="87a0f-143">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-144">操作の名前。</span><span class="sxs-lookup"><span data-stu-id="87a0f-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="87a0f-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="87a0f-145">ParameterTypes</span></span>  
 <span data-ttu-id="87a0f-146">データ型 : string array</span><span class="sxs-lookup"><span data-stu-id="87a0f-146">Data type: string array</span></span>  
  
 <span data-ttu-id="87a0f-147">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-148">操作のパラメーターの型。</span><span class="sxs-lookup"><span data-stu-id="87a0f-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="87a0f-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="87a0f-149">ReplyAction</span></span>  
 <span data-ttu-id="87a0f-150">データ型: string</span><span class="sxs-lookup"><span data-stu-id="87a0f-150">Data type: string</span></span>  
  
 <span data-ttu-id="87a0f-151">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-152">操作の応答メッセージの SOAP アクションの値。</span><span class="sxs-lookup"><span data-stu-id="87a0f-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="87a0f-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="87a0f-153">ReturnType</span></span>  
 <span data-ttu-id="87a0f-154">データ型: string</span><span class="sxs-lookup"><span data-stu-id="87a0f-154">Data type: string</span></span>  
  
 <span data-ttu-id="87a0f-155">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="87a0f-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87a0f-156">操作の戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="87a0f-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87a0f-157">必要条件</span><span class="sxs-lookup"><span data-stu-id="87a0f-157">Requirements</span></span>  
  
|<span data-ttu-id="87a0f-158">MOF</span><span class="sxs-lookup"><span data-stu-id="87a0f-158">MOF</span></span>|<span data-ttu-id="87a0f-159">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="87a0f-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="87a0f-160">名前空間</span><span class="sxs-lookup"><span data-stu-id="87a0f-160">Namespace</span></span>|<span data-ttu-id="87a0f-161">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="87a0f-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87a0f-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="87a0f-162">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
