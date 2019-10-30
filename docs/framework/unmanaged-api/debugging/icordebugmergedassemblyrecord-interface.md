---
title: ICorDebugMergedAssemblyRecord インターフェイス
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 8dc07cb8c2f57ee6f9598c727cbd6de38bf4625f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139189"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="33a94-102">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33a94-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="33a94-103">マージされたアセンブリに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="33a94-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33a94-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="33a94-104">Methods</span></span>  
  
|<span data-ttu-id="33a94-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="33a94-105">Method</span></span>|<span data-ttu-id="33a94-106">説明</span><span class="sxs-lookup"><span data-stu-id="33a94-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33a94-107">GetCulture メソッド</span><span class="sxs-lookup"><span data-stu-id="33a94-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="33a94-108">アセンブリのカルチャ名文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="33a94-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="33a94-109">GetIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="33a94-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="33a94-110">アセンブリのプレフィックス インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="33a94-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="33a94-111">GetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="33a94-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="33a94-112">アセンブリの公開キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="33a94-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="33a94-113">GetPublicKeyToken メソッド</span><span class="sxs-lookup"><span data-stu-id="33a94-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="33a94-114">アセンブリの公開キー トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="33a94-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="33a94-115">GetSimpleName メソッド</span><span class="sxs-lookup"><span data-stu-id="33a94-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="33a94-116">アセンブリの簡易名を取得します。</span><span class="sxs-lookup"><span data-stu-id="33a94-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="33a94-117">GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="33a94-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="33a94-118">アセンブリのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="33a94-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33a94-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="33a94-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33a94-120">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="33a94-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="33a94-121">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="33a94-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33a94-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="33a94-122">Requirements</span></span>  
 <span data-ttu-id="33a94-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a94-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33a94-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33a94-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33a94-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33a94-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33a94-126">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33a94-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a94-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="33a94-127">See also</span></span>

- [<span data-ttu-id="33a94-128">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33a94-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="33a94-129">デバッグ</span><span class="sxs-lookup"><span data-stu-id="33a94-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
