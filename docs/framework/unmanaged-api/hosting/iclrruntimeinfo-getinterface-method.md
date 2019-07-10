---
title: ICLRRuntimeInfo::GetInterface メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4244ef04d6789b7c17ccc8330cb0c26a6c9f3866
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765550"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="6fa17-102">ICLRRuntimeInfo::GetInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="6fa17-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="6fa17-103">現在のプロセスに CLR をロードし、ランタイム、インターフェイス ポインターをなど返します[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)、 [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)、および[IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="6fa17-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="6fa17-104">このメソッドはすべて、 `CorBindTo`\* 関数の[CLR ホスト関数の非推奨とされます](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)セクション。</span><span class="sxs-lookup"><span data-stu-id="6fa17-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa17-105">構文</span><span class="sxs-lookup"><span data-stu-id="6fa17-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fa17-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fa17-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="6fa17-107">[in]コクラスの CLSID のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="6fa17-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="6fa17-108">[in]要求された IID`rclsid`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6fa17-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="6fa17-109">[out]照会されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6fa17-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fa17-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="6fa17-110">Return Value</span></span>  
 <span data-ttu-id="6fa17-111">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="6fa17-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6fa17-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6fa17-112">HRESULT</span></span>|<span data-ttu-id="6fa17-113">説明</span><span class="sxs-lookup"><span data-stu-id="6fa17-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6fa17-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6fa17-114">S_OK</span></span>|<span data-ttu-id="6fa17-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="6fa17-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="6fa17-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6fa17-116">E_POINTER</span></span>|<span data-ttu-id="6fa17-117">`ppUnk` が null です。</span><span class="sxs-lookup"><span data-stu-id="6fa17-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="6fa17-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6fa17-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6fa17-119">メモリが不足は、要求を処理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fa17-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="6fa17-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="6fa17-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="6fa17-121">別のランタイムは、従来の CLR バージョン 2 のアクティブ化ポリシーに既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="6fa17-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fa17-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="6fa17-122">Remarks</span></span>  
 <span data-ttu-id="6fa17-123">このメソッドにより、CLR が読み込まれますが、初期化されていません。</span><span class="sxs-lookup"><span data-stu-id="6fa17-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="6fa17-124">次の表は、サポートされている組み合わせ`rclsid`と`riid`します。</span><span class="sxs-lookup"><span data-stu-id="6fa17-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="6fa17-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="6fa17-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="6fa17-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="6fa17-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="6fa17-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="6fa17-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="6fa17-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="6fa17-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="6fa17-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6fa17-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="6fa17-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6fa17-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="6fa17-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6fa17-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="6fa17-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6fa17-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="6fa17-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="6fa17-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="6fa17-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="6fa17-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="6fa17-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="6fa17-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="6fa17-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="6fa17-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="6fa17-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6fa17-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="6fa17-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6fa17-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fa17-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="6fa17-139">Requirements</span></span>  
 <span data-ttu-id="6fa17-140">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa17-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa17-141">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6fa17-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6fa17-142">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6fa17-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fa17-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa17-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa17-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fa17-144">See also</span></span>

- [<span data-ttu-id="6fa17-145">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fa17-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="6fa17-146">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fa17-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="6fa17-147">ホスティング</span><span class="sxs-lookup"><span data-stu-id="6fa17-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
