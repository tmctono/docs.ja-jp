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
ms.openlocfilehash: 295deeec2e8eb42ccaa4d0cfb8b08b32438d047c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120251"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="4fc41-102">ICLRRuntimeInfo::GetInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="4fc41-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="4fc41-103">現在のプロセスに CLR を読み込み、 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)、 [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)、 [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)などのランタイムインターフェイスポインターを返します。</span><span class="sxs-lookup"><span data-stu-id="4fc41-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="4fc41-104">このメソッドは、[非推奨の CLR ホスト関数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)セクション内のすべての `CorBindTo`\* 関数を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4fc41-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc41-105">構文</span><span class="sxs-lookup"><span data-stu-id="4fc41-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fc41-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4fc41-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="4fc41-107">からコクラスの CLSID インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4fc41-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="4fc41-108">から要求された `rclsid` インターフェイスの IID。</span><span class="sxs-lookup"><span data-stu-id="4fc41-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="4fc41-109">入出力クエリされたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4fc41-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fc41-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="4fc41-110">Return Value</span></span>  
 <span data-ttu-id="4fc41-111">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="4fc41-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4fc41-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4fc41-112">HRESULT</span></span>|<span data-ttu-id="4fc41-113">説明</span><span class="sxs-lookup"><span data-stu-id="4fc41-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4fc41-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4fc41-114">S_OK</span></span>|<span data-ttu-id="4fc41-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="4fc41-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="4fc41-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4fc41-116">E_POINTER</span></span>|<span data-ttu-id="4fc41-117">`ppUnk` が null です。</span><span class="sxs-lookup"><span data-stu-id="4fc41-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="4fc41-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4fc41-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4fc41-119">要求を処理するのに十分なメモリがありません。</span><span class="sxs-lookup"><span data-stu-id="4fc41-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="4fc41-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="4fc41-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="4fc41-121">以前の CLR バージョン2のアクティブ化ポリシーに、別のランタイムが既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="4fc41-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fc41-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="4fc41-122">Remarks</span></span>  
 <span data-ttu-id="4fc41-123">このメソッドを使用すると、CLR が読み込まれますが、初期化されません。</span><span class="sxs-lookup"><span data-stu-id="4fc41-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="4fc41-124">次の表は、`rclsid` と `riid`でサポートされている組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="4fc41-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="4fc41-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="4fc41-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="4fc41-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="4fc41-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="4fc41-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="4fc41-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="4fc41-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="4fc41-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="4fc41-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4fc41-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="4fc41-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4fc41-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="4fc41-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4fc41-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="4fc41-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4fc41-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="4fc41-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="4fc41-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="4fc41-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="4fc41-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="4fc41-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="4fc41-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="4fc41-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="4fc41-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="4fc41-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="4fc41-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="4fc41-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="4fc41-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4fc41-139">［要件］</span><span class="sxs-lookup"><span data-stu-id="4fc41-139">Requirements</span></span>  
 <span data-ttu-id="4fc41-140">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fc41-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fc41-141">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="4fc41-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4fc41-142">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4fc41-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fc41-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fc41-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc41-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fc41-144">See also</span></span>

- [<span data-ttu-id="4fc41-145">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4fc41-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="4fc41-146">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4fc41-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="4fc41-147">ホスティング</span><span class="sxs-lookup"><span data-stu-id="4fc41-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
