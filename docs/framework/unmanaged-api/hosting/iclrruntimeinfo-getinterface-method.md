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
ms.openlocfilehash: 2f229e421cc69f2ff45110233c4c6c36d7a1fc4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771762"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="e5193-102">ICLRRuntimeInfo::GetInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="e5193-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="e5193-103">現在のプロセスに CLR をロードし、ランタイム、インターフェイス ポインターをなど返します[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)、 [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)、および[IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5193-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="e5193-104">このメソッドはすべて、 `CorBindTo`\* 関数の[CLR ホスト関数の非推奨とされます](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)セクション。</span><span class="sxs-lookup"><span data-stu-id="e5193-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5193-105">構文</span><span class="sxs-lookup"><span data-stu-id="e5193-105">Syntax</span></span>  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5193-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5193-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="e5193-107">[in]コクラスの CLSID のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="e5193-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="e5193-108">[in]要求された IID`rclsid`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="e5193-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="e5193-109">[out]照会されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5193-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5193-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="e5193-110">Return Value</span></span>  
 <span data-ttu-id="e5193-111">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="e5193-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e5193-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5193-112">HRESULT</span></span>|<span data-ttu-id="e5193-113">説明</span><span class="sxs-lookup"><span data-stu-id="e5193-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5193-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5193-114">S_OK</span></span>|<span data-ttu-id="e5193-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="e5193-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="e5193-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e5193-116">E_POINTER</span></span>|<span data-ttu-id="e5193-117">`ppUnk` が null です。</span><span class="sxs-lookup"><span data-stu-id="e5193-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="e5193-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e5193-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e5193-119">メモリが不足は、要求を処理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5193-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="e5193-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="e5193-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="e5193-121">別のランタイムは、従来の CLR バージョン 2 のアクティブ化ポリシーに既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="e5193-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5193-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5193-122">Remarks</span></span>  
 <span data-ttu-id="e5193-123">このメソッドにより、CLR が読み込まれますが、初期化されていません。</span><span class="sxs-lookup"><span data-stu-id="e5193-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="e5193-124">次の表は、サポートされている組み合わせ`rclsid`と`riid`します。</span><span class="sxs-lookup"><span data-stu-id="e5193-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="e5193-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="e5193-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="e5193-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="e5193-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="e5193-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="e5193-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="e5193-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="e5193-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="e5193-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e5193-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="e5193-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e5193-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="e5193-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e5193-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="e5193-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e5193-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="e5193-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="e5193-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="e5193-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="e5193-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="e5193-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="e5193-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="e5193-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e5193-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="e5193-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e5193-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="e5193-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e5193-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5193-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5193-139">Requirements</span></span>  
 <span data-ttu-id="e5193-140">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5193-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5193-141">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e5193-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e5193-142">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e5193-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5193-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5193-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5193-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5193-144">See also</span></span>

- [<span data-ttu-id="e5193-145">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5193-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="e5193-146">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5193-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e5193-147">ホスティング</span><span class="sxs-lookup"><span data-stu-id="e5193-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
