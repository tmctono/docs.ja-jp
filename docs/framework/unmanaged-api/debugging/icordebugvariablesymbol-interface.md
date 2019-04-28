---
title: ICorDebugVariableSymbol インターフェイス
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c7cdababd1e4b5fae4f5e48a654f861b708a6e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930118"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="e12c5-102">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e12c5-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="e12c5-103">変数のデバッグ シンボル情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="e12c5-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e12c5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e12c5-104">Methods</span></span>  
  
|<span data-ttu-id="e12c5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e12c5-105">Method</span></span>|<span data-ttu-id="e12c5-106">説明</span><span class="sxs-lookup"><span data-stu-id="e12c5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e12c5-107">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="e12c5-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="e12c5-108">変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="e12c5-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="e12c5-109">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="e12c5-109">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="e12c5-110">変数のサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="e12c5-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="e12c5-111">GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="e12c5-111">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="e12c5-112">ローカル変数のマネージド スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e12c5-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="e12c5-113">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="e12c5-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="e12c5-114">変数の値をバイト配列として取得します。</span><span class="sxs-lookup"><span data-stu-id="e12c5-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="e12c5-115">SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="e12c5-115">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="e12c5-116">バイト配列の値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="e12c5-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e12c5-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="e12c5-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e12c5-118">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="e12c5-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e12c5-119">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="e12c5-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e12c5-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="e12c5-120">Requirements</span></span>  
 <span data-ttu-id="e12c5-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12c5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e12c5-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e12c5-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e12c5-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e12c5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e12c5-124">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e12c5-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12c5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e12c5-125">See also</span></span>

- [<span data-ttu-id="e12c5-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e12c5-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e12c5-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e12c5-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
