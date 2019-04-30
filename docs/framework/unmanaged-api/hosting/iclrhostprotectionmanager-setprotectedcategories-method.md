---
title: ICLRHostProtectionManager::SetProtectedCategories メソッド
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63b6e85b6abe20e9e1f0b00648a06a31735e63c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944639"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="e7a6b-102">ICLRHostProtectionManager::SetProtectedCategories メソッド</span><span class="sxs-lookup"><span data-stu-id="e7a6b-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="e7a6b-103">部分的に信頼されたコードで実行されているを禁止するマネージ型とメンバーのカテゴリを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a6b-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7a6b-104">Syntax</span></span>  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7a6b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7a6b-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="e7a6b-106">[in]組み合わせた[EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)部分的に信頼されたコードで実行されているを禁止するマネージ型とメンバーのカテゴリを示す値。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7a6b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="e7a6b-107">Return Value</span></span>  
  
|<span data-ttu-id="e7a6b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7a6b-108">HRESULT</span></span>|<span data-ttu-id="e7a6b-109">説明</span><span class="sxs-lookup"><span data-stu-id="e7a6b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7a6b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7a6b-110">S_OK</span></span>|<span data-ttu-id="e7a6b-111">`SetProtectedCategories` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="e7a6b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e7a6b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e7a6b-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e7a6b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e7a6b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e7a6b-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-115">The call timed out.</span></span>|  
|<span data-ttu-id="e7a6b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e7a6b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e7a6b-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e7a6b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e7a6b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e7a6b-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e7a6b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e7a6b-120">E_FAIL</span></span>|<span data-ttu-id="e7a6b-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e7a6b-122">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e7a6b-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7a6b-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="e7a6b-124">Remarks</span></span>  
 <span data-ttu-id="e7a6b-125">各`EApiCategories`値はマネージ型とメンバーの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="e7a6b-126">`EApiCategories`列挙と`SetProtectedCategories`メソッドは直接関係をマネージ<xref:System.Security.Permissions.HostProtectionAttribute>を記載したカテゴリに対応する機能を公開するマネージ型とメンバーをマークするために使用するクラスを`EApiCategories`します。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="e7a6b-127">詳細については、次を参照してください。<xref:System.Security.Permissions.HostProtectionAttribute>と<xref:System.Security.Permissions.HostProtectionResource>に直接対応する列挙体`EApiCategories`します。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7a6b-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="e7a6b-128">Requirements</span></span>  
 <span data-ttu-id="e7a6b-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7a6b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7a6b-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7a6b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7a6b-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e7a6b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7a6b-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7a6b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a6b-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7a6b-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="e7a6b-134">EApiCategories 列挙型</span><span class="sxs-lookup"><span data-stu-id="e7a6b-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="e7a6b-135">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7a6b-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e7a6b-136">ICLRHostProtectionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7a6b-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
