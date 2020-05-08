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
ms.openlocfilehash: 17bf4c92b1e1347a8fe790c8df5937de0f95df4d
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895084"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="48cd1-102">ICorDebugAppDomainEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="48cd1-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="48cd1-103">現在のカーソル位置から開始して、指定した数のアプリケーションドメインをコレクションから取得します。</span><span class="sxs-lookup"><span data-stu-id="48cd1-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48cd1-104">構文</span><span class="sxs-lookup"><span data-stu-id="48cd1-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48cd1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48cd1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="48cd1-106">から取得するアプリケーションドメインの数。</span><span class="sxs-lookup"><span data-stu-id="48cd1-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="48cd1-107">入出力ポインターの配列。各ポインターは、アプリケーションドメインを表す、の各オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="48cd1-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="48cd1-108">入出力実際に返されたアプリケーションドメインの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="48cd1-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="48cd1-109">が1の場合`celt` 、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="48cd1-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48cd1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="48cd1-110">Requirements</span></span>  
 <span data-ttu-id="48cd1-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48cd1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48cd1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48cd1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48cd1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48cd1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48cd1-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48cd1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
