---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1aabc5783e66893d13aed60e04d7ea5f6547c68
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773571"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="61f3f-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="61f3f-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="61f3f-103">指定したファイル パスにあるアセンブリのデータをバインドするアセンブリ id を取得します。</span><span class="sxs-lookup"><span data-stu-id="61f3f-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f3f-104">構文</span><span class="sxs-lookup"><span data-stu-id="61f3f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61f3f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61f3f-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="61f3f-106">[in]評価するファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="61f3f-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="61f3f-107">[in]値、 [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)アセンブリの id の種類を示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="61f3f-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="61f3f-108">将来の機能拡張を提供します。</span><span class="sxs-lookup"><span data-stu-id="61f3f-108">Provided for future extensibility.</span></span> <span data-ttu-id="61f3f-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) バージョン 2.0 をサポートする唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="61f3f-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="61f3f-110">[out]非透過的なアセンブリの id データを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="61f3f-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="61f3f-111">[入力、出力]サイズへのポインター`pwzBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="61f3f-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61f3f-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="61f3f-112">Return Value</span></span>  
  
|<span data-ttu-id="61f3f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61f3f-113">HRESULT</span></span>|<span data-ttu-id="61f3f-114">説明</span><span class="sxs-lookup"><span data-stu-id="61f3f-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61f3f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="61f3f-115">S_OK</span></span>|<span data-ttu-id="61f3f-116">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="61f3f-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="61f3f-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="61f3f-117">E_INVALIDARG</span></span>|<span data-ttu-id="61f3f-118">指定された`pwzFilePath`が null です。</span><span class="sxs-lookup"><span data-stu-id="61f3f-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="61f3f-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="61f3f-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="61f3f-120">サイズ`pwzBuffer`が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="61f3f-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="61f3f-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="61f3f-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="61f3f-122">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="61f3f-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="61f3f-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="61f3f-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="61f3f-124">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="61f3f-124">The call timed out.</span></span>|  
|<span data-ttu-id="61f3f-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="61f3f-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="61f3f-126">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="61f3f-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="61f3f-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="61f3f-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="61f3f-128">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="61f3f-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="61f3f-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61f3f-129">E_FAIL</span></span>|<span data-ttu-id="61f3f-130">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="61f3f-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="61f3f-131">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="61f3f-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="61f3f-132">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="61f3f-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61f3f-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="61f3f-133">Remarks</span></span>  
 <span data-ttu-id="61f3f-134">`GetBindingIdentityFromFile` 通常は 2 回呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="61f3f-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="61f3f-135">最初の呼び出しには、null 値が指定されています`pwzBuffer`、メソッドは、適切なサイズを返しますと`pcchBufferSize`します。</span><span class="sxs-lookup"><span data-stu-id="61f3f-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="61f3f-136">2 番目の呼び出しは、適切に割り当てられたバッファーを提供し、完了時にデータを実際のバッファーでメソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="61f3f-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61f3f-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="61f3f-137">Requirements</span></span>  
 <span data-ttu-id="61f3f-138">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f3f-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61f3f-139">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61f3f-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61f3f-140">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="61f3f-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61f3f-141">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61f3f-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f3f-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="61f3f-142">See also</span></span>

- [<span data-ttu-id="61f3f-143">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61f3f-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="61f3f-144">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61f3f-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="61f3f-145">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61f3f-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
