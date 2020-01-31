---
title: ICorProfilerInfo2::EnumModuleFrozenObjects メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
ms.openlocfilehash: 27b3037459ac4f995e37515f6e96c28449c80a4f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862946"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="bac10-102">ICorProfilerInfo2::EnumModuleFrozenObjects メソッド</span><span class="sxs-lookup"><span data-stu-id="bac10-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="bac10-103">指定したモジュール内の固定されたオブジェクトを反復処理できる列挙子を取得します。このメソッドは互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="bac10-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac10-104">構文</span><span class="sxs-lookup"><span data-stu-id="bac10-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bac10-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bac10-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="bac10-106">から列挙される固定オブジェクトを含むモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="bac10-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="bac10-107">入出力固定されたオブジェクトを列挙する[ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md)インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bac10-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bac10-108">要件</span><span class="sxs-lookup"><span data-stu-id="bac10-108">Requirements</span></span>  
 <span data-ttu-id="bac10-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac10-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bac10-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bac10-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bac10-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bac10-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bac10-112">**.NET Framework のバージョン:** 3.5、3.0 SP1、3.0、2.0 SP1、2.0</span><span class="sxs-lookup"><span data-stu-id="bac10-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac10-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="bac10-113">See also</span></span>

- [<span data-ttu-id="bac10-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bac10-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="bac10-115">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bac10-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
