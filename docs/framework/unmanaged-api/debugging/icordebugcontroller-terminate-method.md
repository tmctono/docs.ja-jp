---
title: ICorDebugController::Terminate メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: eade3fd5d946c44ae4a77c571f762709de3cef40
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976565"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="d7f3f-102">ICorDebugController::Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="d7f3f-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="d7f3f-103">指定された終了コードを使用してプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="d7f3f-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7f3f-104">このメソッドは、Win32 `TerminateProcess`関数のラッパーです。</span><span class="sxs-lookup"><span data-stu-id="d7f3f-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="d7f3f-105">したがって`Terminate` 、は、Win32 `TerminateProcess`関数が使用するのと同じ方法で終了コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7f3f-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f3f-106">構文</span><span class="sxs-lookup"><span data-stu-id="d7f3f-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7f3f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7f3f-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="d7f3f-108">から終了コードを表す数値。</span><span class="sxs-lookup"><span data-stu-id="d7f3f-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="d7f3f-109">有効な数値は、Winbase. h で定義されています。</span><span class="sxs-lookup"><span data-stu-id="d7f3f-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7f3f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7f3f-110">Remarks</span></span>  
 <span data-ttu-id="d7f3f-111">が呼び出されたときに`Terminate`プロセスが停止された場合は、このプロセスを続行する必要があります。これを行うに[は、デバッガー](icordebugcontroller-continue-method.md)が、" [ExitProcess](icordebugmanagedcallback-exitprocess-method.md) " または " [managedcallback:: exitappdomain](icordebugmanagedcallback-exitappdomain-method.md) callback" を使用して終了の確認を受け取るようにします。</span><span class="sxs-lookup"><span data-stu-id="d7f3f-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7f3f-112">このメソッドは、アプリケーションドメインによって実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d7f3f-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="d7f3f-113">つまり、 <xref:System.AppDomain>レベルでは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d7f3f-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f3f-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7f3f-114">Requirements</span></span>  
 <span data-ttu-id="d7f3f-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7f3f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f3f-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7f3f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7f3f-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7f3f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7f3f-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f3f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f3f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7f3f-119">See also</span></span>
