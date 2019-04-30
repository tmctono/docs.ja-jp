---
title: ICorDebugAppDomainEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fefc933cc84fede1f3dea16d4b13e09801a96e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996152"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="373f3-102">ICorDebugAppDomainEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="373f3-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="373f3-103">現在のカーソル位置から、コレクションから指定されたアプリケーション ドメイン数を取得します。</span><span class="sxs-lookup"><span data-stu-id="373f3-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="373f3-104">構文</span><span class="sxs-lookup"><span data-stu-id="373f3-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="373f3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="373f3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="373f3-106">[in]取得するアプリケーション ドメインの数。</span><span class="sxs-lookup"><span data-stu-id="373f3-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="373f3-107">[out]アプリケーション ドメインを表す ICorDebugAppDomain オブジェクトを指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="373f3-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="373f3-108">[out]実際に返されるアプリケーション ドメインの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="373f3-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="373f3-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="373f3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="373f3-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="373f3-110">Requirements</span></span>  
 <span data-ttu-id="373f3-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="373f3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="373f3-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="373f3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="373f3-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="373f3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="373f3-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="373f3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
