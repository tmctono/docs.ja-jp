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
ms.openlocfilehash: a2b76cb59a95082e0cf9c0884b8277cca3c8fe8d
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976071"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="43a26-102">ICorDebugEval2::NewStringWithLength メソッド</span><span class="sxs-lookup"><span data-stu-id="43a26-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="43a26-103">指定したコンテンツを使用して、指定した長さの文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="43a26-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43a26-104">構文</span><span class="sxs-lookup"><span data-stu-id="43a26-104">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43a26-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43a26-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="43a26-106">から文字列値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="43a26-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="43a26-107">から文字列の長さ。</span><span class="sxs-lookup"><span data-stu-id="43a26-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43a26-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="43a26-108">Remarks</span></span>  
 <span data-ttu-id="43a26-109">文字列の末尾の null 文字がマネージ文字列に含まれると想定される場合、 `NewStringWithLength`メソッドの呼び出し元は、文字列の長さに末尾の null 文字が含まれていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43a26-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="43a26-110">文字列は常に、スレッドが現在実行されているアプリケーションドメインで作成されます。</span><span class="sxs-lookup"><span data-stu-id="43a26-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43a26-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="43a26-111">Requirements</span></span>  
 <span data-ttu-id="43a26-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43a26-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43a26-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43a26-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43a26-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43a26-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43a26-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43a26-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
