---
title: ICLRValidator::Validate メソッド
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178062"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="017b3-102">ICLRValidator::Validate メソッド</span><span class="sxs-lookup"><span data-stu-id="017b3-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="017b3-103">指定されたファイル内のポータブル実行可能 (PE) または Microsoft 中間言語 (MSIL) を検証します。</span><span class="sxs-lookup"><span data-stu-id="017b3-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="017b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="017b3-104">Syntax</span></span>  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="017b3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="017b3-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="017b3-106">[in]検証エラーを処理`IVEHandler`するインスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="017b3-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="017b3-107">[in]現在<xref:System.AppDomain>の .</span><span class="sxs-lookup"><span data-stu-id="017b3-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="017b3-108">[in]実行する検証の種類を示す[、検証フラグ](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)の値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="017b3-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="017b3-109">[in]検証を終了するまでに許容されるエラーの最大数。</span><span class="sxs-lookup"><span data-stu-id="017b3-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="017b3-110">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="017b3-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="017b3-111">[in]検証するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="017b3-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="017b3-112">[in]ファイル バッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="017b3-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="017b3-113">[in]検証するファイルのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="017b3-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="017b3-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="017b3-114">Return Value</span></span>  
  
|<span data-ttu-id="017b3-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="017b3-115">HRESULT</span></span>|<span data-ttu-id="017b3-116">説明</span><span class="sxs-lookup"><span data-stu-id="017b3-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="017b3-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="017b3-117">S_OK</span></span>|<span data-ttu-id="017b3-118">`Validate`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="017b3-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="017b3-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="017b3-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="017b3-120">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="017b3-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="017b3-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="017b3-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="017b3-122">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="017b3-122">The call timed out.</span></span>|  
|<span data-ttu-id="017b3-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="017b3-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="017b3-124">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="017b3-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="017b3-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="017b3-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="017b3-126">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="017b3-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="017b3-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="017b3-127">E_FAIL</span></span>|<span data-ttu-id="017b3-128">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="017b3-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="017b3-129">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="017b3-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="017b3-130">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="017b3-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="017b3-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="017b3-131">Requirements</span></span>  
 <span data-ttu-id="017b3-132">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="017b3-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="017b3-133">**ヘッダー:** イバリデーター.idl、イバリデーター.h</span><span class="sxs-lookup"><span data-stu-id="017b3-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="017b3-134">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="017b3-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="017b3-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="017b3-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="017b3-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="017b3-136">See also</span></span>

- [<span data-ttu-id="017b3-137">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="017b3-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
