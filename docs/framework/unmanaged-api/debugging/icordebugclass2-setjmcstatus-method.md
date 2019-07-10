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
ms.openlocfilehash: 23f248625753c15a4798ea69a1eb3b377b79f95d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747752"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="8f932-102">ICorDebugClass2::SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="8f932-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="8f932-103">クラスの各メソッドでは、メソッドは、ユーザー定義のコードかどうかを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="8f932-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f932-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f932-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f932-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f932-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="8f932-106">[in]設定`true`メソッドがユーザー定義であることを示すコードは、それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="8f932-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f932-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8f932-107">Remarks</span></span>  
 <span data-ttu-id="8f932-108">マイ コード (のみ JMC) のステッパでは、非ユーザー定義のコードをスキップします。</span><span class="sxs-lookup"><span data-stu-id="8f932-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="8f932-109">ユーザー定義のコードは、デバッグできるコードのサブセットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f932-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="8f932-110">`SetJMCStatus` 場合でも、その他のすべてのメソッドの値を正常に設定、任意のメソッドの値の設定に失敗した場合は、S_FALSE の HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="8f932-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f932-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f932-111">Requirements</span></span>  
 <span data-ttu-id="8f932-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f932-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f932-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f932-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f932-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f932-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f932-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f932-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
