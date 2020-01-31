---
title: ICorDebugValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: e1044386bd6251132703c4e98a0cf2ed267d34e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791137"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="209ef-102">ICorDebugValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="209ef-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="209ef-103">デバッグ中のプロセスの値を表します。</span><span class="sxs-lookup"><span data-stu-id="209ef-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="209ef-104">値には、読み取りまたは書き込みの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="209ef-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="209ef-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="209ef-105">Methods</span></span>  
  
|<span data-ttu-id="209ef-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="209ef-106">Method</span></span>|<span data-ttu-id="209ef-107">説明</span><span class="sxs-lookup"><span data-stu-id="209ef-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="209ef-108">CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="209ef-108">CreateBreakpoint Method</span></span>](icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="209ef-109">このメソッドは、現在実装されていません。</span><span class="sxs-lookup"><span data-stu-id="209ef-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="209ef-110">GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="209ef-110">GetAddress Method</span></span>](icordebugvalue-getaddress-method.md)|<span data-ttu-id="209ef-111">この `ICorDebugValue` オブジェクトのアドレスを取得します。これはデバッグ中のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="209ef-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="209ef-112">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="209ef-112">GetSize Method</span></span>](icordebugvalue-getsize-method.md)|<span data-ttu-id="209ef-113">この `ICorDebugValue` オブジェクトのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="209ef-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="209ef-114">GetType メソッド</span><span class="sxs-lookup"><span data-stu-id="209ef-114">GetType Method</span></span>](icordebugvalue-gettype-method.md)|<span data-ttu-id="209ef-115">この `ICorDebugValue` オブジェクトのプリミティブ型を取得します。</span><span class="sxs-lookup"><span data-stu-id="209ef-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="209ef-116">コメント</span><span class="sxs-lookup"><span data-stu-id="209ef-116">Remarks</span></span>  
 <span data-ttu-id="209ef-117">一般に、値オブジェクトの所有権は、返されるときに渡されます。</span><span class="sxs-lookup"><span data-stu-id="209ef-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="209ef-118">オブジェクトの終了時に、オブジェクトからの参照を削除するのは、受信者の責任です。</span><span class="sxs-lookup"><span data-stu-id="209ef-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="209ef-119">値が取得された場所によっては、プロセスが再開された後も値が有効なままにならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="209ef-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="209ef-120">そのため、一般に、次のように、値は、は、「いいね[:: Continue](icordebugcontroller-continue-method.md)メソッドの呼び出し」で保持するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="209ef-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="209ef-121">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="209ef-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="209ef-122">要件</span><span class="sxs-lookup"><span data-stu-id="209ef-122">Requirements</span></span>  
 <span data-ttu-id="209ef-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="209ef-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="209ef-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="209ef-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="209ef-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="209ef-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="209ef-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="209ef-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="209ef-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="209ef-127">See also</span></span>

- [<span data-ttu-id="209ef-128">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="209ef-128">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="209ef-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="209ef-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
