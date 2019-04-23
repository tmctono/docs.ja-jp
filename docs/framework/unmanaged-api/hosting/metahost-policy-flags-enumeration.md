---
title: METAHOST_POLICY_FLAGS 列挙体
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31ff93b6935c2237a5935c4b40cc30b4129edcd0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230604"
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="4cd51-102">METAHOST_POLICY_FLAGS 列挙体</span><span class="sxs-lookup"><span data-stu-id="4cd51-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="4cd51-103">ほとんどのランタイム ホストに共通するバインディング ポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="4cd51-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="4cd51-104">この列挙体を使って、 [iclrmetahostpolicy::getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="4cd51-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd51-105">構文</span><span class="sxs-lookup"><span data-stu-id="4cd51-105">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="4cd51-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4cd51-106">Members</span></span>  
  
|<span data-ttu-id="4cd51-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="4cd51-107">Member</span></span>|<span data-ttu-id="4cd51-108">説明</span><span class="sxs-lookup"><span data-stu-id="4cd51-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="4cd51-109">共通言語ランタイム (CLR) は、現在のプロセスに読み込まれると見なしません高い互換性、ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="4cd51-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="4cd51-110">代わりと見なされるインストールされている Clr のみと、コンポーネントの基本設定、アセンブリ ファイル自体、宣言されたビルド対象のバージョン、または構成ファイルから派生します。</span><span class="sxs-lookup"><span data-stu-id="4cd51-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="4cd51-111">完全一致が見つからない場合に、hkey_local_machine \software\microsoft の内容に基づいて、バージョンのバインドの結果にアップグレード ポリシーを適用\\します。NETFramework\Policy\Upgrades します。</span><span class="sxs-lookup"><span data-stu-id="4cd51-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="4cd51-112">これと同じ効果を持つ[RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4cd51-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="4cd51-113">呼び出しに提供されたイメージは、新しいプロセスで起動された場合に、バインドの結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="4cd51-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="4cd51-114">現時点では、`GetRequestedRuntime`読み込み可能なランタイムのセットを無視し、インストールされているランタイムのセットに対してバインドします。</span><span class="sxs-lookup"><span data-stu-id="4cd51-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="4cd51-115">このフラグは、ホストの起動時に、EXE がバインドするランタイムを決定するを使用します。</span><span class="sxs-lookup"><span data-stu-id="4cd51-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="4cd51-116">場合、エラー ダイアログ ボックスが表示される`GetRequestedRuntime`は入力パラメーターと互換性があるランタイムを検索できません。</span><span class="sxs-lookup"><span data-stu-id="4cd51-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="4cd51-117">以降では、 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]、このエラー ダイアログ ボックスで、適切な機能を有効にする、ユーザーが希望かどうかを確認する Windows 機能 ダイアログ ボックスの形式を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="4cd51-117">Beginning with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="4cd51-118">`GetRequestedRuntime` バインディング プロセスに追加の入力として、プロセス イメージ (および、対応する構成ファイル) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4cd51-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="4cd51-119">既定では、`GetRequestedRuntime`ことはありません、プロセス イメージのパス (通常は、プロセスを起動するために使用された EXE) にバインドするランタイムを決定するときにします。</span><span class="sxs-lookup"><span data-stu-id="4cd51-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="4cd51-120">`GetRequestedRuntime` 情報は、現在の構成ファイルでないときに、適切な SKU がインストールされているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd51-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="4cd51-121">これにより、アプリケーション、.NET Framework の既定のインストールよりも小さい Sku で適切に失敗する構成ファイルがないことができます。</span><span class="sxs-lookup"><span data-stu-id="4cd51-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="4cd51-122">既定では、 `GetRequestedRuntime` SKU 属性は、構成ファイルで指定されていない場合、適切な SKU がインストールされているかどうかをチェックしません`<supportedRuntime />`要素。</span><span class="sxs-lookup"><span data-stu-id="4cd51-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="4cd51-123">`GetRequestedRuntime` 情報は、現在の構成ファイルでないときに、適切な SKU がインストールされているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd51-123">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="4cd51-124">これにより、アプリケーション、.NET Framework の既定のインストールよりも小さい Sku で適切に失敗する構成ファイルがないことができます。</span><span class="sxs-lookup"><span data-stu-id="4cd51-124">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="4cd51-125">既定では、 `GetRequestedRuntime` SKU 属性は、構成ファイルで指定されていない場合、適切な SKU がインストールされているかどうかをチェックしません`<supportedRuntime />`要素。</span><span class="sxs-lookup"><span data-stu-id="4cd51-125">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="4cd51-126">`GetRequestedRuntime` SEM_FAILCRITICALERRORS を無視する (呼び出すことによって設定されています、 [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242)関数)、エラー ダイアログ ボックスを表示するとします。</span><span class="sxs-lookup"><span data-stu-id="4cd51-126">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="4cd51-127">既定では、SEM_FAILCRITICALERRORS は、エラー ダイアログ ボックスを抑制します。</span><span class="sxs-lookup"><span data-stu-id="4cd51-127">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="4cd51-128">別のプロセスから継承されている可能性があるし、サイレント エラーが実際のシナリオでは望ましくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cd51-128">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cd51-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="4cd51-129">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cd51-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="4cd51-130">Requirements</span></span>  
 <span data-ttu-id="4cd51-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd51-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cd51-132">**ヘッダー:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="4cd51-132">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="4cd51-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="4cd51-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cd51-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cd51-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd51-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cd51-135">See also</span></span>

- [<span data-ttu-id="4cd51-136">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="4cd51-136">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="4cd51-137">GetRequestedRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="4cd51-137">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
