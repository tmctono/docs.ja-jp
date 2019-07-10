---
title: ICLRValidator::FormatEventInfo メソッド
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7354536db483ad93d29fef29745af44a6f90884c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779928"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="9b899-102">ICLRValidator::FormatEventInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="9b899-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="9b899-103">指定した検証エラーに関する詳細なメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="9b899-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b899-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b899-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b899-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b899-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="9b899-106">[in]検証のエラー ハンドラーに渡された HRESULT 値。</span><span class="sxs-lookup"><span data-stu-id="9b899-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="9b899-107">[in]A`VEContext`検証エラーに関するコンテキスト情報を格納しているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9b899-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="9b899-108">[入力、出力]わかりやすいエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="9b899-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="9b899-109">[in]エラー メッセージの最大長。</span><span class="sxs-lookup"><span data-stu-id="9b899-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="9b899-110">[in]メッセージで使用される追加のパラメーターのセーフ配列。</span><span class="sxs-lookup"><span data-stu-id="9b899-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b899-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="9b899-111">Return Value</span></span>  
  
|<span data-ttu-id="9b899-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b899-112">HRESULT</span></span>|<span data-ttu-id="9b899-113">説明</span><span class="sxs-lookup"><span data-stu-id="9b899-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b899-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b899-114">S_OK</span></span>|<span data-ttu-id="9b899-115">`FormatEventInfo` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="9b899-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="9b899-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b899-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b899-117">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="9b899-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b899-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b899-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b899-119">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="9b899-119">The call timed out.</span></span>|  
|<span data-ttu-id="9b899-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b899-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b899-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9b899-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b899-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b899-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b899-123">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="9b899-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b899-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b899-124">E_FAIL</span></span>|<span data-ttu-id="9b899-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9b899-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b899-126">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9b899-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b899-127">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9b899-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b899-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="9b899-128">Requirements</span></span>  
 <span data-ttu-id="9b899-129">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b899-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b899-130">**ヘッダー:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="9b899-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="9b899-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9b899-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b899-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b899-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b899-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b899-133">See also</span></span>

- [<span data-ttu-id="9b899-134">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b899-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="9b899-135">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b899-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
