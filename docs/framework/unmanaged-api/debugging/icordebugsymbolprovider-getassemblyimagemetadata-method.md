---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata メソッド
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0be0722db374ff49541b3c4b68f295774f34163e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953453"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="b84d2-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="b84d2-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="b84d2-103">マージされたアセンブリのメタデータを返します。</span><span class="sxs-lookup"><span data-stu-id="b84d2-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b84d2-104">構文</span><span class="sxs-lookup"><span data-stu-id="b84d2-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b84d2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b84d2-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="b84d2-106">[out]アドレスへのポインター、 [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)マージされたアセンブリのメタデータのアドレスとサイズに関する情報を含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b84d2-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b84d2-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b84d2-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b84d2-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b84d2-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b84d2-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b84d2-109">Requirements</span></span>  
 <span data-ttu-id="b84d2-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b84d2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b84d2-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b84d2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b84d2-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b84d2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b84d2-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b84d2-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84d2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b84d2-114">See also</span></span>

- [<span data-ttu-id="b84d2-115">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b84d2-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b84d2-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b84d2-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
