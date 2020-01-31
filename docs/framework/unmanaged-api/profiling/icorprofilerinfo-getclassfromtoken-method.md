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
ms.openlocfilehash: 841953625235406f013e9f140ad91c7b65680e47
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863954"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="21d73-102">ICorProfilerInfo::GetClassFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="21d73-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="21d73-103">メタデータトークンを指定して、クラスの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="21d73-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="21d73-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="21d73-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="21d73-105">代わりに[ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="21d73-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d73-106">構文</span><span class="sxs-lookup"><span data-stu-id="21d73-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21d73-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="21d73-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="21d73-108">からクラスを含むモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="21d73-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="21d73-109">からクラスを参照する `mdTypeDef` メタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="21d73-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="21d73-110">入出力クラス ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="21d73-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21d73-111">コメント</span><span class="sxs-lookup"><span data-stu-id="21d73-111">Remarks</span></span>  
 <span data-ttu-id="21d73-112">このメソッドは互換性のために残されています。代わりに、すべての型に対して `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` を使用します。</span><span class="sxs-lookup"><span data-stu-id="21d73-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21d73-113">要件</span><span class="sxs-lookup"><span data-stu-id="21d73-113">Requirements</span></span>  
 <span data-ttu-id="21d73-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21d73-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21d73-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21d73-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21d73-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21d73-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21d73-117">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="21d73-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d73-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="21d73-118">See also</span></span>

- [<span data-ttu-id="21d73-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21d73-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
