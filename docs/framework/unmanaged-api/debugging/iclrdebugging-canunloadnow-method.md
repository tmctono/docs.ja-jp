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
ms.openlocfilehash: 16d15101534b88d7da4093dab73b48b5c09a192c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860405"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="beff5-102">ICLRDebugging::CanUnloadNow メソッド</span><span class="sxs-lookup"><span data-stu-id="beff5-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="beff5-103">[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)インターフェイスによって提供されたライブラリがまだ使用中であるか、またはアンロードできるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="beff5-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beff5-104">構文</span><span class="sxs-lookup"><span data-stu-id="beff5-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="beff5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="beff5-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="beff5-106">からターゲットプロセス内のモジュールのベースアドレス。</span><span class="sxs-lookup"><span data-stu-id="beff5-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="beff5-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="beff5-107">Return Value</span></span>  
 <span data-ttu-id="beff5-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="beff5-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="beff5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="beff5-109">HRESULT</span></span>|<span data-ttu-id="beff5-110">説明</span><span class="sxs-lookup"><span data-stu-id="beff5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="beff5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="beff5-111">S_OK</span></span>|<span data-ttu-id="beff5-112">によって参照され`hmodule`ているモジュールは、アンロードできます。</span><span class="sxs-lookup"><span data-stu-id="beff5-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="beff5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="beff5-113">S_FALSE</span></span>|<span data-ttu-id="beff5-114">によって参照され`hmodule`ているモジュールは、引き続き使用されています。</span><span class="sxs-lookup"><span data-stu-id="beff5-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="beff5-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="beff5-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="beff5-116">指定されたモジュールは CLR モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="beff5-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="beff5-117">例外</span><span class="sxs-lookup"><span data-stu-id="beff5-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beff5-118">解説</span><span class="sxs-lookup"><span data-stu-id="beff5-118">Remarks</span></span>  
 <span data-ttu-id="beff5-119">このメソッドは、インターフェイスのすべての`ICorDebug*`インスタンスが解放されているかどうかを確認し、現在[ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)メソッドの呼び出し内にスレッドが存在しないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="beff5-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beff5-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="beff5-120">Requirements</span></span>  
 <span data-ttu-id="beff5-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="beff5-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beff5-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beff5-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beff5-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beff5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beff5-124">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beff5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beff5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="beff5-125">See also</span></span>

- [<span data-ttu-id="beff5-126">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="beff5-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="beff5-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="beff5-127">Debugging</span></span>](index.md)
