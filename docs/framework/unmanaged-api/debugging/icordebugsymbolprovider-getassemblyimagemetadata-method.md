---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata メソッド
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad86c42d0f23de25fe0e5b9123a0dba3695d8d64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964656"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="ee323-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="ee323-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="ee323-103">マージされたアセンブリのメタデータを返します。</span><span class="sxs-lookup"><span data-stu-id="ee323-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee323-104">構文</span><span class="sxs-lookup"><span data-stu-id="ee323-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee323-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee323-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="ee323-106">入出力マージされたアセンブリのメタデータのサイズとアドレスに関する情報を格納して[いる、のオブジェクトの](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ee323-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee323-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee323-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee323-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee323-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee323-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ee323-109">Requirements</span></span>  
 <span data-ttu-id="ee323-110">**・**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee323-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee323-111">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ee323-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee323-112">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="ee323-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee323-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee323-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee323-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee323-114">See also</span></span>

- [<span data-ttu-id="ee323-115">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee323-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="ee323-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee323-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
