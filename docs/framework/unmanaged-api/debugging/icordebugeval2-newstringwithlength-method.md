---
title: ICorDebugEval2::NewStringWithLength メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
ms.openlocfilehash: 3836b6c08098d38516c8a25260fb28998a2317fe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084779"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="a3946-102">ICorDebugEval2::NewStringWithLength メソッド</span><span class="sxs-lookup"><span data-stu-id="a3946-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="a3946-103">指定したコンテンツを使用して、指定した長さの文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="a3946-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3946-104">構文</span><span class="sxs-lookup"><span data-stu-id="a3946-104">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3946-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3946-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="a3946-106">から文字列値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3946-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="a3946-107">から文字列の長さ。</span><span class="sxs-lookup"><span data-stu-id="a3946-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3946-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a3946-108">Remarks</span></span>  
 <span data-ttu-id="a3946-109">文字列の末尾の null 文字がマネージ文字列に含まれることが予想される場合、`NewStringWithLength` メソッドの呼び出し元は、文字列の長さに末尾の null 文字が含まれていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3946-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="a3946-110">文字列は常に、スレッドが現在実行されているアプリケーションドメインで作成されます。</span><span class="sxs-lookup"><span data-stu-id="a3946-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3946-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="a3946-111">Requirements</span></span>  
 <span data-ttu-id="a3946-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3946-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3946-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3946-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3946-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3946-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3946-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3946-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
