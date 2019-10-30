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
ms.openlocfilehash: 4eb6682ac5a8b7788d97f752f249d85886fba0b6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111652"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="2c1a9-102">ICLRDebugging::CanUnloadNow メソッド</span><span class="sxs-lookup"><span data-stu-id="2c1a9-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="2c1a9-103">[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)インターフェイスによって提供されたライブラリがまだ使用中であるか、またはアンロードできるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2c1a9-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1a9-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c1a9-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c1a9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c1a9-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="2c1a9-106">からターゲットプロセス内のモジュールのベースアドレス。</span><span class="sxs-lookup"><span data-stu-id="2c1a9-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c1a9-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2c1a9-107">Return Value</span></span>  
 <span data-ttu-id="2c1a9-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="2c1a9-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2c1a9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c1a9-109">HRESULT</span></span>|<span data-ttu-id="2c1a9-110">説明</span><span class="sxs-lookup"><span data-stu-id="2c1a9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c1a9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c1a9-111">S_OK</span></span>|<span data-ttu-id="2c1a9-112">`hmodule` によって参照されているモジュールはアンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2c1a9-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="2c1a9-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2c1a9-113">S_FALSE</span></span>|<span data-ttu-id="2c1a9-114">`hmodule` によって参照されているモジュールはまだ使用されています。</span><span class="sxs-lookup"><span data-stu-id="2c1a9-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="2c1a9-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="2c1a9-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="2c1a9-116">指定されたモジュールは CLR モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="2c1a9-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2c1a9-117">例外</span><span class="sxs-lookup"><span data-stu-id="2c1a9-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c1a9-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="2c1a9-118">Remarks</span></span>  
 <span data-ttu-id="2c1a9-119">このメソッドは、`ICorDebug*` インターフェイスのすべてのインスタンスが解放されているかどうかを確認し、現在[ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)メソッドの呼び出し内にスレッドが存在しないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c1a9-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c1a9-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="2c1a9-120">Requirements</span></span>  
 <span data-ttu-id="2c1a9-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c1a9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c1a9-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c1a9-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c1a9-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c1a9-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c1a9-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c1a9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1a9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c1a9-125">See also</span></span>

- [<span data-ttu-id="2c1a9-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c1a9-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2c1a9-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2c1a9-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
