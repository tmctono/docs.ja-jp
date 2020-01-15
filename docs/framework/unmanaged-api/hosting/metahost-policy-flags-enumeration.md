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
ms.openlocfilehash: 048286fb9e1af34cd964fb5b21892778f9575d2c
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938202"
---
# <a name="metahost_policy_flags-enumeration"></a><span data-ttu-id="ca9e0-102">METAHOST_POLICY_FLAGS 列挙体</span><span class="sxs-lookup"><span data-stu-id="ca9e0-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="ca9e0-103">ほとんどのランタイムホストに共通のバインドポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="ca9e0-104">この列挙体は、 [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)メソッドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca9e0-105">構文</span><span class="sxs-lookup"><span data-stu-id="ca9e0-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="ca9e0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ca9e0-106">Members</span></span>  
  
|<span data-ttu-id="ca9e0-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="ca9e0-107">Member</span></span>|<span data-ttu-id="ca9e0-108">説明</span><span class="sxs-lookup"><span data-stu-id="ca9e0-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="ca9e0-109">現在のプロセスに読み込まれる共通言語ランタイム (CLR: common language runtime) を考慮しない、互換性の高いポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="ca9e0-110">代わりに、インストールされた CLRs と、コンポーネントの設定 (アセンブリファイル自体、宣言された組み込みバージョン、または構成ファイルから派生したもの) のみを考慮します。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="ca9e0-111">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\\の内容に基づいて完全一致が見つからなかった場合に、バージョンのバインド結果にアップグレードポリシーを適用します。NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="ca9e0-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="ca9e0-112">これは[RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)と同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="ca9e0-113">呼び出しに対して指定されたイメージが新しいプロセスで起動されたかのように、バインディングの結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="ca9e0-114">現時点では、`GetRequestedRuntime` は、一連の読み込み可能なランタイムを無視し、インストールされている一連のランタイムに対してバインドします。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="ca9e0-115">このフラグにより、ホストは、起動時に EXE がバインドされるランタイムを決定できます。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="ca9e0-116">`GetRequestedRuntime` が入力パラメーターと互換性のあるランタイムを見つけられない場合、エラーダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="ca9e0-117">.NET Framework 4.5 以降、このエラーダイアログボックスには、ユーザーが適切な機能を有効にするかどうかを確認する Windows の機能ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-117">Beginning with the .NET Framework 4.5, this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="ca9e0-118">`GetRequestedRuntime` は、プロセスイメージ (およびそれに対応する構成ファイル) をバインドプロセスへの追加入力として使用します。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="ca9e0-119">既定では、`GetRequestedRuntime` は、バインド先のランタイムを決定するときに、プロセスイメージのパス (通常はプロセスの起動に使用された EXE) にフォールバックしません。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="ca9e0-120">構成ファイルに利用できる情報がない場合は、適切な SKU がインストールされているかどうかを確認 `GetRequestedRuntime` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="ca9e0-121">これにより、構成ファイルを持たないアプリケーションは、.NET Framework の既定のインストールよりも小さい Sku では正常に機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="ca9e0-122">既定では、構成ファイル `<supportedRuntime />` 要素で SKU 属性が指定されていない限り、`GetRequestedRuntime` は適切な SKU がインストールされているかどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="ca9e0-123">`GetRequestedRuntime` は、( [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode)関数を呼び出すことによって設定される) SEM_FAILCRITICALERRORS を無視し、エラーダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-123">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function), and show the error dialog box.</span></span> <span data-ttu-id="ca9e0-124">既定では、SEM_FAILCRITICALERRORS はエラーダイアログボックスを表示しません。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-124">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="ca9e0-125">このファイルは別のプロセスから継承されている可能性があり、シナリオによってはサイレントエラーが望ましくない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-125">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca9e0-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca9e0-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca9e0-127">要件</span><span class="sxs-lookup"><span data-stu-id="ca9e0-127">Requirements</span></span>  
 <span data-ttu-id="ca9e0-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca9e0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca9e0-129">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="ca9e0-129">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="ca9e0-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ca9e0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca9e0-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca9e0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9e0-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca9e0-132">See also</span></span>

- [<span data-ttu-id="ca9e0-133">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="ca9e0-133">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="ca9e0-134">GetRequestedRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="ca9e0-134">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
