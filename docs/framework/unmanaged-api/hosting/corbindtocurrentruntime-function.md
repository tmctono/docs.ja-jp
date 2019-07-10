---
title: CorBindToCurrentRuntime 関数
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 505bba3bb5d08c13e29543c20df2daaebc863d12
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768006"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="2cfdd-102">CorBindToCurrentRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="2cfdd-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="2cfdd-103">XML ファイルに格納されているバージョン情報を使用して、共通言語ランタイム (CLR: Common Language Runtime) をプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="2cfdd-104">XML ファイルの形式は、標準的なアプリケーションの構成ファイルの後にモデル化されます。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="2cfdd-105">構成ファイルの詳細については、「[構成ファイル スキーマ](../../../../docs/framework/configure-apps/file-schema/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="2cfdd-106">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-106">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="2cfdd-107">参照してください[、共通言語ランタイムをプロセスに読み込む](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-107">See [Loading the Common Language Runtime into a Process](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cfdd-108">構文</span><span class="sxs-lookup"><span data-stu-id="2cfdd-108">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cfdd-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cfdd-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="2cfdd-110">[in]読み込む CLR のバージョンを示すアプリケーション構成ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="2cfdd-111">ファイル名が完全修飾しない場合、呼び出しを行う実行可能ファイルと同じディレクトリであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="2cfdd-112">読み込むランタイムのバージョンがバージョン属性で説明されている、 [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)構成ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="2cfdd-113">バージョンが指定されていない場合、または場合、`<requiredRuntime>`要素が見つからない場合、マシンにインストールされている CLR の最新バージョンが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="2cfdd-114">[in]`CLSID`のいずれかを実装するコクラスの[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)または[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="2cfdd-115">サポートされている値は CLSID_CorRuntimeHost と CLSID_CLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="2cfdd-116">[入力] 要求するインターフェイスの `IID`。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="2cfdd-117">サポートされている値は IID_ICorRuntimeHost と IID_ICLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2cfdd-118">[out]返されるインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cfdd-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="2cfdd-119">Requirements</span></span>  
 <span data-ttu-id="2cfdd-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cfdd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cfdd-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2cfdd-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2cfdd-122">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2cfdd-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2cfdd-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cfdd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cfdd-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cfdd-124">See also</span></span>

- [<span data-ttu-id="2cfdd-125">CorBindToRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="2cfdd-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="2cfdd-126">CorBindToRuntimeByCfg 関数</span><span class="sxs-lookup"><span data-stu-id="2cfdd-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="2cfdd-127">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="2cfdd-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="2cfdd-128">CorBindToRuntimeHost 関数</span><span class="sxs-lookup"><span data-stu-id="2cfdd-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="2cfdd-129">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cfdd-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="2cfdd-130">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="2cfdd-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
