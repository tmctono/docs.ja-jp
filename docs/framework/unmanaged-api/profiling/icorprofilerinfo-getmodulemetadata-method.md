---
title: ICorProfilerInfo::GetModuleMetaData メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e63cf698e41e70084c9b71bdf58d7ac60723d53
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782790"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="86f00-102">ICorProfilerInfo::GetModuleMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="86f00-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="86f00-103">指定したモジュールにマップされるメタデータ インターフェイス インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="86f00-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f00-104">構文</span><span class="sxs-lookup"><span data-stu-id="86f00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86f00-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="86f00-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="86f00-106">[in]インターフェイス インスタンスのマップされたモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="86f00-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="86f00-107">[in]値、 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)マニフェスト ファイルを開くためのモードを指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="86f00-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="86f00-108">のみ、 `ofRead`、`ofWrite`と`ofNoTransform`のビットが無効です。</span><span class="sxs-lookup"><span data-stu-id="86f00-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="86f00-109">[in]参照 ID (GUID) のメタデータ インターフェイスを持つインスタンスが取得されます。</span><span class="sxs-lookup"><span data-stu-id="86f00-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="86f00-110">参照してください[メタデータ インターフェイス](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)インターフェイスの一覧についてはします。</span><span class="sxs-lookup"><span data-stu-id="86f00-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="86f00-111">[out]メタデータ インターフェイス インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="86f00-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86f00-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="86f00-112">Remarks</span></span>  
 <span data-ttu-id="86f00-113">読み取り/書き込みモードで開かれるメタデータに問い合わせることができますが、その結果、プログラムのメタデータ、実行速度が、コンパイラからと同様に変更が加えられたため、メタデータは最適化できません。</span><span class="sxs-lookup"><span data-stu-id="86f00-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="86f00-114">メタデータを所有している (リソース モジュール) などの一部のモジュールはありません。</span><span class="sxs-lookup"><span data-stu-id="86f00-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="86f00-115">その場合、`GetModuleMetaData`は S_FALSE とで null 値の HRESULT 値を返します \*`ppOut`します。</span><span class="sxs-lookup"><span data-stu-id="86f00-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in \*`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86f00-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="86f00-116">Requirements</span></span>  
 <span data-ttu-id="86f00-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="86f00-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86f00-118">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86f00-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86f00-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86f00-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86f00-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86f00-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f00-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="86f00-121">See also</span></span>

- [<span data-ttu-id="86f00-122">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="86f00-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
