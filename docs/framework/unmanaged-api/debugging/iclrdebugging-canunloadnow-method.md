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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80559ef685a2dbf48d65e0d81432a5edbd5528bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698149"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="99fad-102">ICLRDebugging::CanUnloadNow メソッド</span><span class="sxs-lookup"><span data-stu-id="99fad-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="99fad-103">ライブラリで提供されているかどうかを決定する、 [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)インターフェイスが使用されている、またはアンロードできます。</span><span class="sxs-lookup"><span data-stu-id="99fad-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99fad-104">構文</span><span class="sxs-lookup"><span data-stu-id="99fad-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99fad-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="99fad-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="99fad-106">[in]ターゲット プロセスのモジュールのベース アドレス。</span><span class="sxs-lookup"><span data-stu-id="99fad-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99fad-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="99fad-107">Return Value</span></span>  
 <span data-ttu-id="99fad-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="99fad-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="99fad-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99fad-109">HRESULT</span></span>|<span data-ttu-id="99fad-110">説明</span><span class="sxs-lookup"><span data-stu-id="99fad-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99fad-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="99fad-111">S_OK</span></span>|<span data-ttu-id="99fad-112">によって参照されるモジュール`hmodule`アンロードできます。</span><span class="sxs-lookup"><span data-stu-id="99fad-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="99fad-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="99fad-113">S_FALSE</span></span>|<span data-ttu-id="99fad-114">によって参照されるモジュール`hmodule`使用されています。</span><span class="sxs-lookup"><span data-stu-id="99fad-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="99fad-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="99fad-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="99fad-116">指定されたモジュールが CLR モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="99fad-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="99fad-117">例外</span><span class="sxs-lookup"><span data-stu-id="99fad-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99fad-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="99fad-118">Remarks</span></span>  
 <span data-ttu-id="99fad-119">このメソッドはすべてかどうかをチェックのインスタンス`ICorDebug*`インターフェイスがリリースされた、スレッドがない現在の呼び出し内で、 [iclrdebugging::openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="99fad-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99fad-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="99fad-120">Requirements</span></span>  
 <span data-ttu-id="99fad-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99fad-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99fad-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99fad-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99fad-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99fad-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99fad-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99fad-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99fad-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="99fad-125">See also</span></span>

- [<span data-ttu-id="99fad-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="99fad-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="99fad-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="99fad-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
