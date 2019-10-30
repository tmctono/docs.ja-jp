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
ms.openlocfilehash: 0369cc6d98736542b764e5914d733a9341753b24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088882"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="48c25-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="48c25-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="48c25-103">インターフェイス識別子に基づいて、アプリケーションドメイン内のキャッシュされた Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="48c25-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48c25-104">構文</span><span class="sxs-lookup"><span data-stu-id="48c25-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48c25-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48c25-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="48c25-106">から要求される型の数。</span><span class="sxs-lookup"><span data-stu-id="48c25-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="48c25-107">から取得する Windows ランタイム型のマネージ表現に対応するインターフェイス識別子を格納する配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="48c25-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="48c25-108">入出力`iidsToResolve`のインターフェイス識別子に基づいて、取得された Windows ランタイム型のキャッシュされたマネージ表現を列挙できるようにする、"" "の" "ツール" インターフェイスオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="48c25-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48c25-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="48c25-109">Remarks</span></span>  
 <span data-ttu-id="48c25-110">メソッドが特定のインターフェイス識別子に関する情報の取得に失敗した場合、データの取得に関する問題が原因でエラーが発生した場合、または不明なインターフェイス識別子の `ELEMENT_TYPE_VOID` については、"" の種類 "というコレクション内の対応するエントリの `ELEMENT_TYPE_END` 型になります。</span><span class="sxs-lookup"><span data-stu-id="48c25-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48c25-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="48c25-111">Requirements</span></span>  
 <span data-ttu-id="48c25-112">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="48c25-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="48c25-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48c25-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48c25-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48c25-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48c25-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48c25-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c25-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="48c25-116">See also</span></span>

- [<span data-ttu-id="48c25-117">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48c25-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
