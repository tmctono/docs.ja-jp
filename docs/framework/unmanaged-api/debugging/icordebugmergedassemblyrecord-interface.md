---
title: ICorDebugMergedAssemblyRecord インターフェイス
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1118c879da4376bda0c73368a8b15df4f7a3d014
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180467"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="ed594-102">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ed594-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="ed594-103">マージされたアセンブリに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ed594-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed594-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ed594-104">Methods</span></span>  
  
|<span data-ttu-id="ed594-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ed594-105">Method</span></span>|<span data-ttu-id="ed594-106">説明</span><span class="sxs-lookup"><span data-stu-id="ed594-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed594-107">GetCulture メソッド</span><span class="sxs-lookup"><span data-stu-id="ed594-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="ed594-108">アセンブリのカルチャ名文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="ed594-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="ed594-109">GetIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="ed594-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="ed594-110">アセンブリのプレフィックス インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ed594-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="ed594-111">GetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="ed594-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="ed594-112">アセンブリの公開キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="ed594-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="ed594-113">GetPublicKeyToken メソッド</span><span class="sxs-lookup"><span data-stu-id="ed594-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="ed594-114">アセンブリの公開キー トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="ed594-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="ed594-115">GetSimpleName メソッド</span><span class="sxs-lookup"><span data-stu-id="ed594-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="ed594-116">アセンブリの簡易名を取得します。</span><span class="sxs-lookup"><span data-stu-id="ed594-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="ed594-117">GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="ed594-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="ed594-118">アセンブリのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ed594-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed594-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="ed594-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed594-120">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="ed594-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ed594-121">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="ed594-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed594-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="ed594-122">Requirements</span></span>  
 <span data-ttu-id="ed594-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed594-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed594-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed594-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed594-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed594-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ed594-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ed594-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed594-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed594-127">See also</span></span>

- [<span data-ttu-id="ed594-128">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ed594-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ed594-129">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ed594-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
