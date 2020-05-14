---
title: ICorDebugVariableSymbol インターフェイス
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 412ecbfc03378947e5a578e163034d104718bc91
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397105"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="676d3-102">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="676d3-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="676d3-103">変数のデバッグ シンボル情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="676d3-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="676d3-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="676d3-104">Methods</span></span>  
  
|<span data-ttu-id="676d3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="676d3-105">Method</span></span>|<span data-ttu-id="676d3-106">説明</span><span class="sxs-lookup"><span data-stu-id="676d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="676d3-107">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="676d3-107">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="676d3-108">変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="676d3-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="676d3-109">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="676d3-109">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="676d3-110">変数のサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="676d3-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="676d3-111">GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="676d3-111">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="676d3-112">ローカル変数のマネージド スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="676d3-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="676d3-113">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="676d3-113">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="676d3-114">変数の値をバイト配列として取得します。</span><span class="sxs-lookup"><span data-stu-id="676d3-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="676d3-115">SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="676d3-115">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="676d3-116">バイト配列の値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="676d3-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="676d3-117">解説</span><span class="sxs-lookup"><span data-stu-id="676d3-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="676d3-118">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="676d3-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="676d3-119">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="676d3-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="676d3-120">要件</span><span class="sxs-lookup"><span data-stu-id="676d3-120">Requirements</span></span>  
 <span data-ttu-id="676d3-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="676d3-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="676d3-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="676d3-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="676d3-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="676d3-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="676d3-124">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="676d3-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676d3-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="676d3-125">See also</span></span>

- [<span data-ttu-id="676d3-126">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="676d3-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="676d3-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="676d3-127">Debugging</span></span>](index.md)
