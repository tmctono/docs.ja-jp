---
title: ICorDebugMergedAssemblyRecord::GetVersion メソッド
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb7861e33a02b994c4c29569a811f4e2f3c44cec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762313"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="dd55b-102">ICorDebugMergedAssemblyRecord::GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="dd55b-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="dd55b-103">アセンブリのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd55b-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd55b-104">構文</span><span class="sxs-lookup"><span data-stu-id="dd55b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd55b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd55b-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="dd55b-106">[out] メジャー バージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dd55b-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="dd55b-107">[out] マイナー バージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dd55b-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="dd55b-108">[out] ビルド番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dd55b-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="dd55b-109">[out] リビジョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dd55b-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd55b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="dd55b-110">Remarks</span></span>  
 <span data-ttu-id="dd55b-111">アセンブリのバージョン番号については、<xref:System.Version> クラスのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd55b-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd55b-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd55b-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd55b-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="dd55b-113">Requirements</span></span>  
 <span data-ttu-id="dd55b-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd55b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd55b-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd55b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd55b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd55b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd55b-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd55b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd55b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd55b-118">See also</span></span>

- [<span data-ttu-id="dd55b-119">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd55b-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="dd55b-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd55b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
