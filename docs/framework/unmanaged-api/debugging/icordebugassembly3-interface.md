---
title: ICorDebugAssembly3 インターフェイス
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eecb135e034c3565e805ea776115579488b2a4d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210309"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="4f6fe-102">ICorDebugAssembly3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f6fe-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="4f6fe-103">コンテナー アセンブリとその格納されているアセンブリのサポートを提供する ICorDebugAssembly インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="4f6fe-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f6fe-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4f6fe-104">Methods</span></span>  
  
|<span data-ttu-id="4f6fe-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4f6fe-105">Method</span></span>|<span data-ttu-id="4f6fe-106">説明</span><span class="sxs-lookup"><span data-stu-id="4f6fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f6fe-107">EnumerateContainedAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="4f6fe-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="4f6fe-108">このアセンブリに含まれているアセンブリの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="4f6fe-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="4f6fe-109">GetContainerAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="4f6fe-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="4f6fe-110">この `ICorDebugAssembly3` オブジェクトのコンテナー アセンブリを返します。</span><span class="sxs-lookup"><span data-stu-id="4f6fe-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f6fe-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f6fe-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f6fe-112">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="4f6fe-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="4f6fe-113">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="4f6fe-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f6fe-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f6fe-114">Requirements</span></span>  
 <span data-ttu-id="4f6fe-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f6fe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f6fe-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f6fe-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f6fe-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f6fe-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4f6fe-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="4f6fe-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f6fe-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f6fe-119">See also</span></span>

- [<span data-ttu-id="4f6fe-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f6fe-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4f6fe-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4f6fe-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
