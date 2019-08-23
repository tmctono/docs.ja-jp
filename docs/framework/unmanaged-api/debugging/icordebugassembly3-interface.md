---
title: ICorDebugAssembly3 インターフェイス
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca77360c36ff2cdce7ee47d5c3883dd824c6cef8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959323"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="a6ec5-102">ICorDebugAssembly3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6ec5-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="a6ec5-103">は、このアセンブリインターフェイスを論理的に拡張して、コンテナーアセンブリとそれに含まれるアセンブリのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="a6ec5-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6ec5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a6ec5-104">Methods</span></span>  
  
|<span data-ttu-id="a6ec5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a6ec5-105">Method</span></span>|<span data-ttu-id="a6ec5-106">説明</span><span class="sxs-lookup"><span data-stu-id="a6ec5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6ec5-107">EnumerateContainedAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="a6ec5-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="a6ec5-108">このアセンブリに含まれているアセンブリの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="a6ec5-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="a6ec5-109">GetContainerAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="a6ec5-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="a6ec5-110">この `ICorDebugAssembly3` オブジェクトのコンテナー アセンブリを返します。</span><span class="sxs-lookup"><span data-stu-id="a6ec5-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6ec5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a6ec5-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6ec5-112">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="a6ec5-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="a6ec5-113">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="a6ec5-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6ec5-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6ec5-114">Requirements</span></span>  
 <span data-ttu-id="a6ec5-115">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ec5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ec5-116">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a6ec5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6ec5-117">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="a6ec5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6ec5-118">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6ec5-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ec5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6ec5-119">See also</span></span>

- [<span data-ttu-id="a6ec5-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6ec5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a6ec5-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="a6ec5-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
