---
title: ICorDebugMergedAssemblyRecord インターフェイス
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208721"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="83ecf-102">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83ecf-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="83ecf-103">マージされたアセンブリに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="83ecf-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83ecf-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="83ecf-104">Methods</span></span>  
  
|<span data-ttu-id="83ecf-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="83ecf-105">Method</span></span>|<span data-ttu-id="83ecf-106">説明</span><span class="sxs-lookup"><span data-stu-id="83ecf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83ecf-107">GetCulture メソッド</span><span class="sxs-lookup"><span data-stu-id="83ecf-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="83ecf-108">アセンブリのカルチャ名文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="83ecf-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="83ecf-109">GetIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="83ecf-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="83ecf-110">アセンブリのプレフィックス インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="83ecf-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="83ecf-111">GetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="83ecf-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="83ecf-112">アセンブリの公開キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="83ecf-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="83ecf-113">GetPublicKeyToken メソッド</span><span class="sxs-lookup"><span data-stu-id="83ecf-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="83ecf-114">アセンブリの公開キー トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="83ecf-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="83ecf-115">GetSimpleName メソッド</span><span class="sxs-lookup"><span data-stu-id="83ecf-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="83ecf-116">アセンブリの簡易名を取得します。</span><span class="sxs-lookup"><span data-stu-id="83ecf-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="83ecf-117">GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="83ecf-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="83ecf-118">アセンブリのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="83ecf-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83ecf-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="83ecf-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83ecf-120">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="83ecf-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="83ecf-121">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="83ecf-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83ecf-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="83ecf-122">Requirements</span></span>  
 <span data-ttu-id="83ecf-123">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83ecf-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83ecf-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83ecf-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83ecf-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83ecf-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83ecf-126">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83ecf-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ecf-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="83ecf-127">See also</span></span>

- [<span data-ttu-id="83ecf-128">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="83ecf-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="83ecf-129">デバッグ</span><span class="sxs-lookup"><span data-stu-id="83ecf-129">Debugging</span></span>](index.md)
