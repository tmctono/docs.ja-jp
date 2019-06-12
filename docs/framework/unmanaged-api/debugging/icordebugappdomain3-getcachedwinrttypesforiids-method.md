---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95c84f7f40db0096b26ec448f8f229cdbfe3afb1
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025905"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="2289c-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="2289c-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="2289c-103">インターフェイスの識別子に基づいて、アプリケーション ドメインで、キャッシュ済みの Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="2289c-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2289c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2289c-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2289c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2289c-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="2289c-106">[in]必要な種類の数。</span><span class="sxs-lookup"><span data-stu-id="2289c-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="2289c-107">[in]取得する Windows ランタイム型のマネージ表現に対応するインターフェイスの識別子を含む配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2289c-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="2289c-108">[out]インターフェイス識別子に基づいて、Windows ランタイム型のキャッシュされたマネージ表現の列挙を許可する"ICorDebugTypeEnum"インターフェイス オブジェクトのアドレスへのポインターが取得`iidsToResolve`します。</span><span class="sxs-lookup"><span data-stu-id="2289c-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2289c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2289c-109">Remarks</span></span>  
 <span data-ttu-id="2289c-110">"ICorDebugTypeEnum"コレクション内の対応するエントリの種類には、メソッドは、特定のインターフェイスの識別子の情報を取得する失敗した場合、`ELEMENT_TYPE_END`のデータの取得に問題に起因するエラーまたは`ELEMENT_TYPE_VOID`不明なインターフェイス識別子。</span><span class="sxs-lookup"><span data-stu-id="2289c-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2289c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2289c-111">Requirements</span></span>  
 <span data-ttu-id="2289c-112">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="2289c-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="2289c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2289c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2289c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2289c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2289c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2289c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2289c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2289c-116">See also</span></span>

- [<span data-ttu-id="2289c-117">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2289c-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
