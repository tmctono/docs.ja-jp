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
ms.openlocfilehash: 9326484c6a9f96d245e3c61a0ac3e3465a8a6dcd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616646"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="1b7f0-102">CorBindToRuntimeByCfg 関数</span><span class="sxs-lookup"><span data-stu-id="1b7f0-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="1b7f0-103">XML ファイルから読み取られたバージョン情報を使用して、共通言語ランタイム (CLR) をプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="1b7f0-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b7f0-105">構文</span><span class="sxs-lookup"><span data-stu-id="1b7f0-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1b7f0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b7f0-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="1b7f0-107">から`IStream`XML ファイルを読み取るオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="1b7f0-108">から将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-108">[in] Reserved for future use.</span></span> <span data-ttu-id="1b7f0-109">0 (ゼロ) を値として使用します。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="1b7f0-110">からCLR の起動動作を指定する[STARTUP_FLAGS](startup-flags-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="1b7f0-111">から`CLSID` [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)または[ICLRRuntimeHost](iclrruntimehost-interface.md)のいずれかのインターフェイスを実装するコクラスの。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="1b7f0-112">サポートされている値は CLSID_CorRuntimeHost と CLSID_CLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="1b7f0-113">から`IID` `ICorRuntimeHost` インターフェイスまたは `ICLRRuntimeHost` インターフェイスの。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="1b7f0-114">サポートされている値は IID_ICorRuntimeHost と IID_ICLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="1b7f0-115">入出力返されたインターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b7f0-116">解説</span><span class="sxs-lookup"><span data-stu-id="1b7f0-116">Remarks</span></span>  
 <span data-ttu-id="1b7f0-117">XML ファイルの形式は、標準のアプリケーション構成ファイルの後にモデル化されています。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="1b7f0-118">XML ファイルの詳細については、「[構成ファイルのスキーマ](../../configure-apps/file-schema/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b7f0-119">要件</span><span class="sxs-lookup"><span data-stu-id="1b7f0-119">Requirements</span></span>  
 <span data-ttu-id="1b7f0-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b7f0-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b7f0-121">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1b7f0-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b7f0-122">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1b7f0-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b7f0-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b7f0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b7f0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b7f0-124">See also</span></span>

- [<span data-ttu-id="1b7f0-125">CorBindToCurrentRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="1b7f0-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="1b7f0-126">CorBindToRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="1b7f0-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="1b7f0-127">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="1b7f0-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="1b7f0-128">CorBindToRuntimeHost 関数</span><span class="sxs-lookup"><span data-stu-id="1b7f0-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="1b7f0-129">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b7f0-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="1b7f0-130">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="1b7f0-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
