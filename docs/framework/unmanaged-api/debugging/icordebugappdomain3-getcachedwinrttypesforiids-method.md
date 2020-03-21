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
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179055"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="41755-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="41755-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="41755-103">インターフェイス識別子に基づいて、アプリケーション ドメインにキャッシュされた Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="41755-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41755-104">構文</span><span class="sxs-lookup"><span data-stu-id="41755-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41755-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41755-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="41755-106">[in]必要な型の数。</span><span class="sxs-lookup"><span data-stu-id="41755-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="41755-107">[in]取得する Windows ランタイム型のマネージ表現に対応するインターフェイス識別子を含む配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="41755-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="41755-108">[アウト]で取得した Windows ランタイム型のキャッシュされたマネージ表現の列挙を可能にする "ICorDebugTypeEnum" インターフェイス オブジェクトのアドレスへのポインター `iidsToResolve`。</span><span class="sxs-lookup"><span data-stu-id="41755-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41755-109">解説</span><span class="sxs-lookup"><span data-stu-id="41755-109">Remarks</span></span>  
 <span data-ttu-id="41755-110">メソッドが特定のインターフェイス識別子の情報を取得できない場合、"ICorDebugTypeEnum" コレクション内の対応するエントリは、データ取得`ELEMENT_TYPE_END`の問題または`ELEMENT_TYPE_VOID`不明なインターフェイス識別子のエラーの種類を持ちます。</span><span class="sxs-lookup"><span data-stu-id="41755-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41755-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="41755-111">Requirements</span></span>  
 <span data-ttu-id="41755-112">**プラットフォーム:** ウィンドウズランタイム</span><span class="sxs-lookup"><span data-stu-id="41755-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="41755-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41755-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41755-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41755-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41755-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41755-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41755-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="41755-116">See also</span></span>

- [<span data-ttu-id="41755-117">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41755-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
