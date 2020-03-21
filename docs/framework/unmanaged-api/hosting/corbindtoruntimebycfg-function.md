---
title: CorBindToRuntimeByCfg 関数
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: 4fbc6e7ea531f65a6b1cd0ec93f4847ab8e4fe83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178242"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="ab938-102">CorBindToRuntimeByCfg 関数</span><span class="sxs-lookup"><span data-stu-id="ab938-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="ab938-103">XML ファイルから読み取られたバージョン情報を使用して、共通言語ランタイム (CLR) をプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ab938-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="ab938-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ab938-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab938-105">構文</span><span class="sxs-lookup"><span data-stu-id="ab938-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab938-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ab938-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="ab938-107">[in]XML ファイルを`IStream`読み取るオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ab938-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="ab938-108">[in]将来の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="ab938-108">[in] Reserved for future use.</span></span> <span data-ttu-id="ab938-109">値として 0 (ゼロ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab938-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="ab938-110">[in]CLR のスタートアップ動作を指定する[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="ab938-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="ab938-111">[in]`CLSID`インターフェイス[を実装](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)するコクラスの[。](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ab938-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="ab938-112">サポートされている値は CLSID_CorRuntimeHost と CLSID_CLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="ab938-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="ab938-113">[in]`ICorRuntimeHost`または`IID``ICLRRuntimeHost`インターフェイスのいずれか。</span><span class="sxs-lookup"><span data-stu-id="ab938-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="ab938-114">サポートされている値は IID_ICorRuntimeHost と IID_ICLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="ab938-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ab938-115">[アウト]返されたインターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ab938-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab938-116">解説</span><span class="sxs-lookup"><span data-stu-id="ab938-116">Remarks</span></span>  
 <span data-ttu-id="ab938-117">XML ファイルの形式は、標準アプリケーション構成ファイルをモデルにしています。</span><span class="sxs-lookup"><span data-stu-id="ab938-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="ab938-118">XML ファイルの詳細については、「[構成ファイル スキーマ](../../../../docs/framework/configure-apps/file-schema/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab938-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab938-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab938-119">Requirements</span></span>  
 <span data-ttu-id="ab938-120">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab938-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab938-121">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ab938-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab938-122">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab938-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab938-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab938-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab938-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab938-124">See also</span></span>

- [<span data-ttu-id="ab938-125">CorBindToCurrentRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="ab938-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="ab938-126">CorBindToRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="ab938-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="ab938-127">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="ab938-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="ab938-128">CorBindToRuntimeHost 関数</span><span class="sxs-lookup"><span data-stu-id="ab938-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="ab938-129">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab938-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="ab938-130">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="ab938-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
