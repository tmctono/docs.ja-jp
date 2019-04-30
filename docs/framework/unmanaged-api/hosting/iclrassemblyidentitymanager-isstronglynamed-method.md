---
title: ICLRAssemblyIdentityManager::IsStronglyNamed メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 166583f690fc7ed80f80cf2cf5cd5b0348708cc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970158"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="f742e-102">ICLRAssemblyIdentityManager::IsStronglyNamed メソッド</span><span class="sxs-lookup"><span data-stu-id="f742e-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="f742e-103">指定したアセンブリが厳密な名前かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f742e-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f742e-104">構文</span><span class="sxs-lookup"><span data-stu-id="f742e-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f742e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f742e-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="f742e-106">[in]評価するアセンブリの非透過の標準アセンブリの id データ。</span><span class="sxs-lookup"><span data-stu-id="f742e-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="f742e-107">[out]`true`、アセンブリによって参照される場合、`pwzAssemblyIdentity`パラメーターが厳密に名前付き、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="f742e-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f742e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f742e-108">Return Value</span></span>  
  
|<span data-ttu-id="f742e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f742e-109">HRESULT</span></span>|<span data-ttu-id="f742e-110">説明</span><span class="sxs-lookup"><span data-stu-id="f742e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f742e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f742e-111">S_OK</span></span>|<span data-ttu-id="f742e-112">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="f742e-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="f742e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f742e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f742e-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="f742e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f742e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f742e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f742e-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="f742e-116">The call timed out.</span></span>|  
|<span data-ttu-id="f742e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f742e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f742e-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f742e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f742e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f742e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f742e-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="f742e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f742e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f742e-121">E_FAIL</span></span>|<span data-ttu-id="f742e-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f742e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f742e-123">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f742e-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f742e-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f742e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f742e-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="f742e-125">Requirements</span></span>  
 <span data-ttu-id="f742e-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f742e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f742e-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f742e-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f742e-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f742e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f742e-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f742e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f742e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f742e-130">See also</span></span>

- [<span data-ttu-id="f742e-131">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f742e-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
