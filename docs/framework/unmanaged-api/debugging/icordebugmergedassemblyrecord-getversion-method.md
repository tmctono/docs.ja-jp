---
title: ICorDebugMergedAssemblyRecord::GetVersion メソッド
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 5dc9995e88086da854d2e9382cef81b229ff9dc9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178685"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="fafdb-102">ICorDebugMergedAssemblyRecord::GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="fafdb-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="fafdb-103">アセンブリのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="fafdb-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fafdb-104">構文</span><span class="sxs-lookup"><span data-stu-id="fafdb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fafdb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fafdb-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="fafdb-106">[out] メジャー バージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fafdb-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="fafdb-107">[out] マイナー バージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fafdb-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="fafdb-108">[out] ビルド番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fafdb-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="fafdb-109">[out] リビジョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fafdb-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fafdb-110">解説</span><span class="sxs-lookup"><span data-stu-id="fafdb-110">Remarks</span></span>  
 <span data-ttu-id="fafdb-111">アセンブリのバージョン番号については、<xref:System.Version> クラスのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fafdb-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fafdb-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fafdb-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fafdb-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="fafdb-113">Requirements</span></span>  
 <span data-ttu-id="fafdb-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fafdb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fafdb-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fafdb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fafdb-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fafdb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fafdb-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fafdb-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fafdb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="fafdb-118">See also</span></span>

- [<span data-ttu-id="fafdb-119">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fafdb-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="fafdb-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fafdb-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
