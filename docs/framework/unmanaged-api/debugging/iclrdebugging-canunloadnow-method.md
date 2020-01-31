---
title: ICLRDebugging::CanUnloadNow メソッド
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
ms.openlocfilehash: 41b2e009f8f017a72147232015ea2357ae922ca1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793646"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="be205-102">ICLRDebugging::CanUnloadNow メソッド</span><span class="sxs-lookup"><span data-stu-id="be205-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="be205-103">[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)インターフェイスによって提供されたライブラリがまだ使用中であるか、またはアンロードできるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="be205-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be205-104">構文</span><span class="sxs-lookup"><span data-stu-id="be205-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be205-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be205-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="be205-106">からターゲットプロセス内のモジュールのベースアドレス。</span><span class="sxs-lookup"><span data-stu-id="be205-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be205-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="be205-107">Return Value</span></span>  
 <span data-ttu-id="be205-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="be205-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="be205-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be205-109">HRESULT</span></span>|<span data-ttu-id="be205-110">説明</span><span class="sxs-lookup"><span data-stu-id="be205-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be205-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="be205-111">S_OK</span></span>|<span data-ttu-id="be205-112">`hmodule` によって参照されているモジュールはアンロードできます。</span><span class="sxs-lookup"><span data-stu-id="be205-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="be205-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="be205-113">S_FALSE</span></span>|<span data-ttu-id="be205-114">`hmodule` によって参照されているモジュールはまだ使用されています。</span><span class="sxs-lookup"><span data-stu-id="be205-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="be205-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="be205-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="be205-116">指定されたモジュールは CLR モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="be205-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="be205-117">例外</span><span class="sxs-lookup"><span data-stu-id="be205-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be205-118">コメント</span><span class="sxs-lookup"><span data-stu-id="be205-118">Remarks</span></span>  
 <span data-ttu-id="be205-119">このメソッドは、`ICorDebug*` インターフェイスのすべてのインスタンスが解放されているかどうかを確認し、現在[ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)メソッドの呼び出し内にスレッドが存在しないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="be205-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be205-120">要件</span><span class="sxs-lookup"><span data-stu-id="be205-120">Requirements</span></span>  
 <span data-ttu-id="be205-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be205-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be205-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be205-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be205-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be205-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be205-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be205-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be205-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="be205-125">See also</span></span>

- [<span data-ttu-id="be205-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="be205-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="be205-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="be205-127">Debugging</span></span>](index.md)
