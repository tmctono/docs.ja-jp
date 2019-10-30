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
ms.openlocfilehash: 19d6a76d62680be91a7b9721912ca528edde7511
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126755"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="55e92-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="55e92-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="55e92-103">指定したファイルパスにあるアセンブリのアセンブリ id バインドデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="55e92-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e92-104">構文</span><span class="sxs-lookup"><span data-stu-id="55e92-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55e92-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55e92-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="55e92-106">から評価されるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="55e92-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="55e92-107">からアセンブリの id 型を示す[Eclrassemblyidentity flags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="55e92-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="55e92-108">将来の拡張のために提供されます。</span><span class="sxs-lookup"><span data-stu-id="55e92-108">Provided for future extensibility.</span></span> <span data-ttu-id="55e92-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) バージョン2.0 でサポートされている唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="55e92-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="55e92-110">入出力非透過アセンブリ id データを格納しているバッファー。</span><span class="sxs-lookup"><span data-stu-id="55e92-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="55e92-111">[入力、出力]`pwzBuffer`のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="55e92-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55e92-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="55e92-112">Return Value</span></span>  
  
|<span data-ttu-id="55e92-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55e92-113">HRESULT</span></span>|<span data-ttu-id="55e92-114">説明</span><span class="sxs-lookup"><span data-stu-id="55e92-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55e92-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="55e92-115">S_OK</span></span>|<span data-ttu-id="55e92-116">メソッドが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="55e92-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="55e92-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="55e92-117">E_INVALIDARG</span></span>|<span data-ttu-id="55e92-118">指定された `pwzFilePath` が null です。</span><span class="sxs-lookup"><span data-stu-id="55e92-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="55e92-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="55e92-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="55e92-120">`pwzBuffer` のサイズが小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="55e92-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="55e92-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55e92-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55e92-122">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="55e92-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55e92-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55e92-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55e92-124">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="55e92-124">The call timed out.</span></span>|  
|<span data-ttu-id="55e92-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55e92-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55e92-126">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="55e92-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55e92-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55e92-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55e92-128">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="55e92-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55e92-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55e92-129">E_FAIL</span></span>|<span data-ttu-id="55e92-130">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="55e92-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55e92-131">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="55e92-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55e92-132">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="55e92-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55e92-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="55e92-133">Remarks</span></span>  
 <span data-ttu-id="55e92-134">通常、`GetBindingIdentityFromFile` は2回呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="55e92-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="55e92-135">最初の呼び出しでは `pwzBuffer`に null 値が指定され、メソッドは `pcchBufferSize`で適切なサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="55e92-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="55e92-136">2番目の呼び出しでは、適切に割り当てられたバッファーが提供され、メソッドは完了時に実際のバッファーデータと共にを返します。</span><span class="sxs-lookup"><span data-stu-id="55e92-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e92-137">［要件］</span><span class="sxs-lookup"><span data-stu-id="55e92-137">Requirements</span></span>  
 <span data-ttu-id="55e92-138">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55e92-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e92-139">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="55e92-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55e92-140">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="55e92-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55e92-141">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e92-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e92-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="55e92-142">See also</span></span>

- [<span data-ttu-id="55e92-143">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55e92-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="55e92-144">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55e92-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="55e92-145">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55e92-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
