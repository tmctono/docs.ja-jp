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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8f5e9a909a752dd8dc70bfc1c683b4611715f31
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767966"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="df9be-102">CorBindToRuntimeByCfg 関数</span><span class="sxs-lookup"><span data-stu-id="df9be-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="df9be-103">XML ファイルから読み取られるバージョン情報を使用して、共通言語ランタイム (CLR) をプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="df9be-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="df9be-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="df9be-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df9be-105">構文</span><span class="sxs-lookup"><span data-stu-id="df9be-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="df9be-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df9be-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="df9be-107">[in]ポインター、`IStream`を XML ファイルを読み込むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="df9be-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="df9be-108">[in]将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="df9be-108">[in] Reserved for future use.</span></span> <span data-ttu-id="df9be-109">値として 0 (ゼロ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="df9be-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="df9be-110">[in]値、 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) CLR のスタートアップ動作を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="df9be-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="df9be-111">[in]`CLSID`のいずれかを実装するコクラスの[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)または[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="df9be-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="df9be-112">サポートされている値は CLSID_CorRuntimeHost と CLSID_CLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="df9be-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="df9be-113">[in]`IID`のいずれか、`ICorRuntimeHost`または`ICLRRuntimeHost`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="df9be-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="df9be-114">サポートされている値は IID_ICorRuntimeHost と IID_ICLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="df9be-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="df9be-115">[out]返されるインターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="df9be-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df9be-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="df9be-116">Remarks</span></span>  
 <span data-ttu-id="df9be-117">XML ファイルの形式は、標準的なアプリケーションの構成ファイルの後にモデル化されます。</span><span class="sxs-lookup"><span data-stu-id="df9be-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="df9be-118">XML ファイルの詳細については、次を参照してください。[構成ファイル スキーマ](../../../../docs/framework/configure-apps/file-schema/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="df9be-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df9be-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="df9be-119">Requirements</span></span>  
 <span data-ttu-id="df9be-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df9be-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df9be-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df9be-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df9be-122">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df9be-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df9be-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df9be-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9be-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="df9be-124">See also</span></span>

- [<span data-ttu-id="df9be-125">CorBindToCurrentRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="df9be-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="df9be-126">CorBindToRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="df9be-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="df9be-127">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="df9be-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="df9be-128">CorBindToRuntimeHost 関数</span><span class="sxs-lookup"><span data-stu-id="df9be-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="df9be-129">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df9be-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="df9be-130">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="df9be-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
