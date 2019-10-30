---
title: 'GetAssemblyImageMetadata Method Provider:: メソッド'
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: fb08df3b594e0c34dfe4ca791983b0c111239b23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138912"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="f1959-102">GetAssemblyImageMetadata Method Provider:: メソッド</span><span class="sxs-lookup"><span data-stu-id="f1959-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="f1959-103">マージされたアセンブリのメタデータを返します。</span><span class="sxs-lookup"><span data-stu-id="f1959-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1959-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1959-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1959-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1959-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="f1959-106">入出力マージされたアセンブリのメタデータのサイズとアドレスに関する情報を格納して[いる、のオブジェクトの](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1959-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1959-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1959-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1959-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1959-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1959-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="f1959-109">Requirements</span></span>  
 <span data-ttu-id="f1959-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1959-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1959-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1959-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1959-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1959-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1959-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1959-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1959-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1959-114">See also</span></span>

- [<span data-ttu-id="f1959-115">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1959-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f1959-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1959-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
