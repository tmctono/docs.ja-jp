---
title: ICorDebugClass2::SetJMCStatus メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed6570e11008e52d4b1f97c2dc90e2ccbef2e35
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471382"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="4ef79-102">ICorDebugClass2::SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="4ef79-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="4ef79-103">クラスの各メソッドでは、メソッドは、ユーザー定義のコードかどうかを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="4ef79-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ef79-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ef79-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ef79-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ef79-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="4ef79-106">[in]設定`true`メソッドがユーザー定義であることを示すコードは、それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="4ef79-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ef79-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ef79-107">Remarks</span></span>  
 <span data-ttu-id="4ef79-108">マイ コード (のみ JMC) のステッパでは、非ユーザー定義のコードをスキップします。</span><span class="sxs-lookup"><span data-stu-id="4ef79-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="4ef79-109">ユーザー定義のコードは、デバッグできるコードのサブセットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ef79-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="4ef79-110">`SetJMCStatus` 場合でも、その他のすべてのメソッドの値を正常に設定、任意のメソッドの値の設定に失敗した場合は、S_FALSE の HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="4ef79-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ef79-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4ef79-111">Requirements</span></span>  
 <span data-ttu-id="4ef79-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ef79-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ef79-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ef79-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ef79-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ef79-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ef79-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ef79-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
