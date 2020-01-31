---
title: ICorDebugVariableSymbol インターフェイス
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 9d17bc92dcae9e906dfe18d7665fbf489d278234
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790871"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="1c296-102">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c296-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="1c296-103">変数のデバッグ シンボル情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c296-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c296-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1c296-104">Methods</span></span>  
  
|<span data-ttu-id="1c296-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1c296-105">Method</span></span>|<span data-ttu-id="1c296-106">説明</span><span class="sxs-lookup"><span data-stu-id="1c296-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c296-107">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="1c296-107">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="1c296-108">変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c296-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="1c296-109">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="1c296-109">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="1c296-110">変数のサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c296-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="1c296-111">GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="1c296-111">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="1c296-112">ローカル変数のマネージド スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1c296-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="1c296-113">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="1c296-113">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="1c296-114">変数の値をバイト配列として取得します。</span><span class="sxs-lookup"><span data-stu-id="1c296-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="1c296-115">SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="1c296-115">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="1c296-116">バイト配列の値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="1c296-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c296-117">コメント</span><span class="sxs-lookup"><span data-stu-id="1c296-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c296-118">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="1c296-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="1c296-119">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="1c296-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c296-120">要件</span><span class="sxs-lookup"><span data-stu-id="1c296-120">Requirements</span></span>  
 <span data-ttu-id="1c296-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c296-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c296-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c296-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c296-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c296-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c296-124">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c296-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c296-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c296-125">See also</span></span>

- [<span data-ttu-id="1c296-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c296-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1c296-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="1c296-127">Debugging</span></span>](index.md)
