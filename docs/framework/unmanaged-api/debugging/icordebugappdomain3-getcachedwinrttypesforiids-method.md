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
ms.openlocfilehash: ed1d7ad95b7c8474121994d0f54557c1c36cb531
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917377"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="337a6-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="337a6-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="337a6-103">キャッシュされた列挙子を取得[!INCLUDE[wrt](../../../../includes/wrt-md.md)]アプリケーション ドメイン内の型、インターフェイスの id に基づいています。</span><span class="sxs-lookup"><span data-stu-id="337a6-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337a6-104">構文</span><span class="sxs-lookup"><span data-stu-id="337a6-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="337a6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="337a6-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="337a6-106">[in]必要な種類の数。</span><span class="sxs-lookup"><span data-stu-id="337a6-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="337a6-107">[in]マネージ表現に対応するインターフェイスの識別子を含む配列へのポインター、[!INCLUDE[wrt](../../../../includes/wrt-md.md)]を取得する型。</span><span class="sxs-lookup"><span data-stu-id="337a6-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="337a6-108">[out]キャッシュの列挙を許可する"ICorDebugTypeEnum"インターフェイス オブジェクトのアドレスへのポインターの表現の管理、[!INCLUDE[wrt](../../../../includes/wrt-md.md)]インターフェイス識別子に基づいて、型が取得`iidsToResolve`します。</span><span class="sxs-lookup"><span data-stu-id="337a6-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="337a6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="337a6-109">Remarks</span></span>  
 <span data-ttu-id="337a6-110">"ICorDebugTypeEnum"コレクション内の対応するエントリの種類には、メソッドは、特定のインターフェイスの識別子の情報を取得する失敗した場合、`ELEMENT_TYPE_END`のデータの取得に問題に起因するエラーまたは`ELEMENT_TYPE_VOID`不明なインターフェイス識別子。</span><span class="sxs-lookup"><span data-stu-id="337a6-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="337a6-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="337a6-111">Requirements</span></span>  
 <span data-ttu-id="337a6-112">**プラットフォーム:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337a6-112">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="337a6-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="337a6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="337a6-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="337a6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="337a6-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337a6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337a6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="337a6-116">See also</span></span>

- [<span data-ttu-id="337a6-117">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="337a6-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
