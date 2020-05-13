---
title: ICorDebugMergedAssemblyRecord::GetVersion メソッド
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: cad71080c86e92beb318722db86011b09ce02e91
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207624"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="faa5c-102">ICorDebugMergedAssemblyRecord::GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="faa5c-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="faa5c-103">アセンブリのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="faa5c-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faa5c-104">構文</span><span class="sxs-lookup"><span data-stu-id="faa5c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faa5c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="faa5c-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="faa5c-106">[out] メジャー バージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="faa5c-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="faa5c-107">[out] マイナー バージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="faa5c-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="faa5c-108">[out] ビルド番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="faa5c-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="faa5c-109">[out] リビジョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="faa5c-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faa5c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="faa5c-110">Remarks</span></span>  
 <span data-ttu-id="faa5c-111">アセンブリのバージョン番号については、<xref:System.Version> クラスのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="faa5c-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="faa5c-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="faa5c-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faa5c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="faa5c-113">Requirements</span></span>  
 <span data-ttu-id="faa5c-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faa5c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faa5c-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faa5c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faa5c-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faa5c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faa5c-117">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faa5c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa5c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="faa5c-118">See also</span></span>

- [<span data-ttu-id="faa5c-119">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="faa5c-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="faa5c-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="faa5c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
