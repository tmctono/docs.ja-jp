---
title: 'ICorDebugMergedAssemblyRecord:: GetVersion メソッド'
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 0c89d0749281da412bbf71400d51bee1ed651fbe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129771"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="2d6c6-102">ICorDebugMergedAssemblyRecord:: GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="2d6c6-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="2d6c6-103">アセンブリのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d6c6-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d6c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d6c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d6c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d6c6-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="2d6c6-106">[out] メジャー バージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2d6c6-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="2d6c6-107">[out] マイナー バージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2d6c6-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="2d6c6-108">[out] ビルド番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2d6c6-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="2d6c6-109">[out] リビジョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2d6c6-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d6c6-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="2d6c6-110">Remarks</span></span>  
 <span data-ttu-id="2d6c6-111">アセンブリのバージョン番号については、<xref:System.Version> クラスのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d6c6-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d6c6-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d6c6-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d6c6-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="2d6c6-113">Requirements</span></span>  
 <span data-ttu-id="2d6c6-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d6c6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d6c6-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d6c6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d6c6-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d6c6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d6c6-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d6c6-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d6c6-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d6c6-118">See also</span></span>

- [<span data-ttu-id="2d6c6-119">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d6c6-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="2d6c6-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d6c6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
