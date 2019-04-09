---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata メソッド
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0be0722db374ff49541b3c4b68f295774f34163e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104131"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="f49d3-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="f49d3-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="f49d3-103">マージされたアセンブリのメタデータを返します。</span><span class="sxs-lookup"><span data-stu-id="f49d3-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f49d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="f49d3-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f49d3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f49d3-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="f49d3-106">[out]アドレスへのポインター、 [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)マージされたアセンブリのメタデータのアドレスとサイズに関する情報を含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f49d3-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f49d3-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f49d3-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f49d3-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f49d3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f49d3-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="f49d3-109">Requirements</span></span>  
 <span data-ttu-id="f49d3-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f49d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f49d3-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f49d3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f49d3-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f49d3-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f49d3-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="f49d3-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f49d3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f49d3-114">See also</span></span>

- [<span data-ttu-id="f49d3-115">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f49d3-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f49d3-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f49d3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
