---
title: ICorDebugVariableSymbol インターフェイス
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fb2538894184c19bc107ce52cbef3ac86a97345
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967975"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="40059-102">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40059-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="40059-103">変数のデバッグ シンボル情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="40059-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40059-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="40059-104">Methods</span></span>  
  
|<span data-ttu-id="40059-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="40059-105">Method</span></span>|<span data-ttu-id="40059-106">説明</span><span class="sxs-lookup"><span data-stu-id="40059-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40059-107">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="40059-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="40059-108">変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="40059-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="40059-109">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="40059-109">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="40059-110">変数のサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="40059-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="40059-111">GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="40059-111">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="40059-112">ローカル変数のマネージド スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="40059-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="40059-113">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="40059-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="40059-114">変数の値をバイト配列として取得します。</span><span class="sxs-lookup"><span data-stu-id="40059-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="40059-115">SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="40059-115">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="40059-116">バイト配列の値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="40059-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40059-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="40059-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40059-118">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="40059-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="40059-119">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="40059-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40059-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="40059-120">Requirements</span></span>  
 <span data-ttu-id="40059-121">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40059-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40059-122">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="40059-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40059-123">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="40059-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40059-124">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40059-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40059-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="40059-125">See also</span></span>

- [<span data-ttu-id="40059-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40059-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="40059-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="40059-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
