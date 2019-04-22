---
title: ICorProfilerInfo::GetClassFromToken メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 580c554c968819ba4ef2ba52edeb5e754d33ac1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185267"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="a19ef-102">ICorProfilerInfo::GetClassFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="a19ef-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="a19ef-103">指定したメタデータ トークン、クラスの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="a19ef-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="a19ef-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="a19ef-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a19ef-105">使用[icorprofilerinfo 2::getclassfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="a19ef-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a19ef-106">構文</span><span class="sxs-lookup"><span data-stu-id="a19ef-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a19ef-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a19ef-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="a19ef-108">[in]クラスを含むモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="a19ef-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="a19ef-109">[in]`mdTypeDef`クラスを参照するメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="a19ef-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="a19ef-110">[out]クラス ID へのポインター</span><span class="sxs-lookup"><span data-stu-id="a19ef-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a19ef-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a19ef-111">Remarks</span></span>  
 <span data-ttu-id="a19ef-112">このメソッドは廃止されています。代わりに、`ICorProfilerInfo2::GetClassFromTokenAndTypeArgs`すべての種類。</span><span class="sxs-lookup"><span data-stu-id="a19ef-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a19ef-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="a19ef-113">Requirements</span></span>  
 <span data-ttu-id="a19ef-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a19ef-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a19ef-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a19ef-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a19ef-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a19ef-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a19ef-117">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a19ef-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a19ef-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a19ef-118">See also</span></span>

- [<span data-ttu-id="a19ef-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a19ef-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
