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
ms.openlocfilehash: a862dd3f6a9c10c6b3a5a0bb41208d351c4ca9f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125700"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="848fc-102">ICorDebugClass2::SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="848fc-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="848fc-103">クラスの各メソッドについて、メソッドがユーザー定義のコードかどうかを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="848fc-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="848fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="848fc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="848fc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="848fc-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="848fc-106">からメソッドがユーザー定義コードであることを示すには `true` に設定します。それ以外の場合は、を `false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="848fc-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="848fc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="848fc-107">Remarks</span></span>  
 <span data-ttu-id="848fc-108">マイコードのみ (JMC) のステッパは、ユーザー定義ではないコードをスキップします。</span><span class="sxs-lookup"><span data-stu-id="848fc-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="848fc-109">ユーザー定義コードは、デバッグ可能なコードのサブセットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="848fc-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="848fc-110">`SetJMCStatus` は、他のすべてのメソッドの値が正常に設定されていても、どのメソッドにも値を設定できない場合に、S_FALSE の HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="848fc-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="848fc-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="848fc-111">Requirements</span></span>  
 <span data-ttu-id="848fc-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="848fc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="848fc-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="848fc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="848fc-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="848fc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="848fc-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="848fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
