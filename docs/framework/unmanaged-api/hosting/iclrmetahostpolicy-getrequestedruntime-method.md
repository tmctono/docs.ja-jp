---
title: ICLRMetaHostPolicy::GetRequestedRuntime メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy.GetRequestedRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type:
- apiref
ms.openlocfilehash: 37167b7a9aefa6cd9d5e4df043e8bbc1b0514261
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504122"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a><span data-ttu-id="35930-102">ICLRMetaHostPolicy::GetRequestedRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="35930-102">ICLRMetaHostPolicy::GetRequestedRuntime Method</span></span>

<span data-ttu-id="35930-103">ホスト ポリシー、マネージド アセンブリ、バージョン文字列、および構成ストリームに基づいて、適切な共通言語ランタイム (CLR) のバージョンへのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="35930-103">Provides an interface to a preferred version of the common language runtime (CLR) based on a hosting policy, managed assembly, version string, and configuration stream.</span></span> <span data-ttu-id="35930-104">このメソッドは、実際には CLR の読み込みもアクティブ化も行いませんが、単にポリシー結果を表す[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)インターフェイスを返します。</span><span class="sxs-lookup"><span data-stu-id="35930-104">This method does not actually load or activate the CLR, but simply returns the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that represents the policy result.</span></span> <span data-ttu-id="35930-105">このメソッドは、 [Getrequestedruntimeinfo](getrequestedruntimeinfo-function.md)、 [getrequestedruntimeinfo](getrequestedruntimeversion-function.md)、 [corbindtoruntimehost](corbindtoruntimehost-function.md)、 [Corbindtoruntimebycfg](corbindtoruntimebycfg-function.md)、および[getcorrequiredversion](getcorrequiredversion-function.md)メソッドを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="35930-105">This method supersedes the [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md), and [GetCORRequiredVersion](getcorrequiredversion-function.md) methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="35930-106">構文</span><span class="sxs-lookup"><span data-stu-id="35930-106">Syntax</span></span>

```cpp
HRESULT GetRequestedRuntime(
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,
    [in]  LPCWSTR pwzBinary,
    [in]  IStream *pCfgStream,
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,
    [in, out]  DWORD *pcchVersion,
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,
    [in, out]  DWORD *pcchImageVersion,
    [out] DWORD *pdwConfigFlags,
    [in]  REFIID  riid
    [out, iid_is(riid), retval] LPVOID *ppRuntime);
```

## <a name="parameters"></a><span data-ttu-id="35930-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35930-107">Parameters</span></span>

|<span data-ttu-id="35930-108">名前</span><span class="sxs-lookup"><span data-stu-id="35930-108">Name</span></span>|<span data-ttu-id="35930-109">説明</span><span class="sxs-lookup"><span data-stu-id="35930-109">Description</span></span>|
|----------|-----------------|
|`dwPolicyFlags`|<span data-ttu-id="35930-110">[in] 必須。</span><span class="sxs-lookup"><span data-stu-id="35930-110">[in] Required.</span></span> <span data-ttu-id="35930-111">バインディングポリシーを表す[METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md)列挙体のメンバーと、任意の数の修飾子を指定します。</span><span class="sxs-lookup"><span data-stu-id="35930-111">Specifies a member of the [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) enumeration, representing a binding policy, and any number of modifiers.</span></span> <span data-ttu-id="35930-112">現在使用できるポリシーは[METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md)のみです。</span><span class="sxs-lookup"><span data-stu-id="35930-112">The only policy that is currently available is [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).</span></span><br /><br /> <span data-ttu-id="35930-113">修飾子には、 [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md)、 [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md)、 [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md)、 [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md)、および[METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="35930-113">Modifiers include [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md), and [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md).</span></span>|
|`pwzBinary`|<span data-ttu-id="35930-114">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="35930-114">[in] Optional.</span></span> <span data-ttu-id="35930-115">アセンブリのファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="35930-115">Specifies the assembly file path.</span></span>|
|`pCfgStream`|<span data-ttu-id="35930-116">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="35930-116">[in] Optional.</span></span> <span data-ttu-id="35930-117">構成ファイルを <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType> として指定します。</span><span class="sxs-lookup"><span data-stu-id="35930-117">Specifies the configuration file as a <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span></span>|
|`pwzVersion`|<span data-ttu-id="35930-118">[in、out] 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="35930-118">[in, out] Optional.</span></span> <span data-ttu-id="35930-119">読み込む適切な CLR のバージョンを指定するか返します。 </span><span class="sxs-lookup"><span data-stu-id="35930-119">Specifies or returns the preferred CLR version to be loaded.</span></span>|
|`pcchVersion`|<span data-ttu-id="35930-120">[in、out] 必須です。</span><span class="sxs-lookup"><span data-stu-id="35930-120">[in, out] Required.</span></span> <span data-ttu-id="35930-121">バッファー オーバーランを回避するため、入力として必要なサイズの `pwzVersion` を指定します。</span><span class="sxs-lookup"><span data-stu-id="35930-121">Specifies the expected size of `pwzVersion` as input, to avoid buffer overruns.</span></span> <span data-ttu-id="35930-122">`pwzVersion` が null の場合、`GetRequestedRuntime` が返されるときに、`pcchVersion` には必要なサイズの `pwzVersion` が含まれて、事前の割り当てが可能になります。それ以外の場合、`pcchVersion` には `pwzVersion` に書き込まれる文字数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="35930-122">If `pwzVersion` is null, `pcchVersion` contains the expected size of `pwzVersion` when `GetRequestedRuntime` returns, to allow pre-allocation; otherwise, `pcchVersion` contains the number of characters written to `pwzVersion`.</span></span>|
|`pwzImageVersion`|<span data-ttu-id="35930-123">[out] 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="35930-123">[out] Optional.</span></span> <span data-ttu-id="35930-124">が返されるときに `GetRequestedRuntime` 、返される[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)インターフェイスに対応する CLR バージョンを格納します。</span><span class="sxs-lookup"><span data-stu-id="35930-124">When `GetRequestedRuntime` returns, contains the CLR version corresponding to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that is returned.</span></span>|
|`pcchImageVersion`|<span data-ttu-id="35930-125">[in、out] 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="35930-125">[in, out] Optional.</span></span> <span data-ttu-id="35930-126">バッファー オーバーランを回避するため、入力として `pwzImageVersion` のサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="35930-126">Specifies the size of `pwzImageVersion` as input to avoid buffer overruns.</span></span> <span data-ttu-id="35930-127">`pwzImageVersion` が null の場合、`GetRequestedRuntime` が返されるとき、`pcchImageVersion` には必要なサイズの `pwzImageVersion` が含まれて、事前の割り当てが可能になります。</span><span class="sxs-lookup"><span data-stu-id="35930-127">If `pwzImageVersion` is null, `pcchImageVersion` contains the required size of `pwzImageVersion` when `GetRequestedRuntime` returns, to allow pre-allocation.</span></span>|
|`pdwConfigFlags`|<span data-ttu-id="35930-128">[out] 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="35930-128">[out] Optional.</span></span> <span data-ttu-id="35930-129">が `GetRequestedRuntime` バインドプロセス中に構成ファイルを使用する場合、が返されるときに、 `pdwConfigFlags` 要素に属性セットがあるかどうか、 [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) [\<startup>](../../configure-apps/file-schema/startup/startup-element.md) `useLegacyV2RuntimeActivationPolicy` および属性の値が含まれているかどうかを示す METAHOST_CONFIG_FLAGS 値を格納します。</span><span class="sxs-lookup"><span data-stu-id="35930-129">If `GetRequestedRuntime` uses a configuration file during the binding process, when it returns, `pdwConfigFlags` contains a [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) value that indicates whether the [\<startup>](../../configure-apps/file-schema/startup/startup-element.md) element has the `useLegacyV2RuntimeActivationPolicy` attribute set, and the value of the attribute.</span></span> <span data-ttu-id="35930-130">に関連する値を取得するには、 [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md)マスクをに適用し `pdwConfigFlags` `useLegacyV2RuntimeActivationPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="35930-130">Apply the [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) mask to `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|
|`riid`|<span data-ttu-id="35930-131">から要求された[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)インターフェイスのインターフェイス識別子 IID_ICLRRuntimeInfo を指定します。</span><span class="sxs-lookup"><span data-stu-id="35930-131">[in] Specifies the interface identifier IID_ICLRRuntimeInfo for the requested [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>|
|`ppRuntime`|<span data-ttu-id="35930-132">入出力が返されるときに `GetRequestedRuntime` 、対応する[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)インターフェイスへのポインターを格納します。</span><span class="sxs-lookup"><span data-stu-id="35930-132">[out] When `GetRequestedRuntime` returns, contains a pointer to the corresponding [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>|

## <a name="remarks"></a><span data-ttu-id="35930-133">解説</span><span class="sxs-lookup"><span data-stu-id="35930-133">Remarks</span></span>

<span data-ttu-id="35930-134">このメソッドが正常に実行されると、`<configuration><runtime>` セクション内の構成ストリームに次の要素の 1 つ以上が存在する場合 にのみ、返されるランタイム インターフェイスの追加フラグと現在の既定のスタートアップ フラグが結合するという副作用が発生します。</span><span class="sxs-lookup"><span data-stu-id="35930-134">When this method succeeds, it has the side effect of combining additional flags with the current default startup flags of the returned runtime interface, if and only if one or more of the following elements exist in the configuration stream within the `<configuration><runtime>` section:</span></span>

- <span data-ttu-id="35930-135">`<gcServer enabled="true"/>` により `STARTUP_SERVER_GC` が設定されます。</span><span class="sxs-lookup"><span data-stu-id="35930-135">`<gcServer enabled="true"/>` causes `STARTUP_SERVER_GC` to be set.</span></span>

- <span data-ttu-id="35930-136">`<etwEnable enabled="true"/>` により `STARTUP_ETW` が設定されます。</span><span class="sxs-lookup"><span data-stu-id="35930-136">`<etwEnable enabled="true"/>` causes `STARTUP_ETW` to be set.</span></span>

- <span data-ttu-id="35930-137">`<appDomainResourceMonitoring enabled="true"/>` により `STARTUP_ARM` が設定されます。</span><span class="sxs-lookup"><span data-stu-id="35930-137">`<appDomainResourceMonitoring enabled="true"/>` causes `STARTUP_ARM` to be set.</span></span>

<span data-ttu-id="35930-138">結果として得られる既定の `STARTUP_FLAGS` 値は、上記の既定のスタートアップ フラグの一覧から設定される値のビットごとの OR の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="35930-138">The resulting default `STARTUP_FLAGS` value is the bitwise OR combination of the values that are set from the preceding list with the default startup flags.</span></span>

## <a name="return-value"></a><span data-ttu-id="35930-139">戻り値</span><span class="sxs-lookup"><span data-stu-id="35930-139">Return Value</span></span>

<span data-ttu-id="35930-140">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="35930-140">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="35930-141">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35930-141">HRESULT</span></span>|<span data-ttu-id="35930-142">説明</span><span class="sxs-lookup"><span data-stu-id="35930-142">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="35930-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="35930-143">S_OK</span></span>|<span data-ttu-id="35930-144">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="35930-144">The method completed successfully.</span></span>|
|<span data-ttu-id="35930-145">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="35930-145">E_POINTER</span></span>|<span data-ttu-id="35930-146">`pwzVersion` は null 以外で、`pcchVersion` は null です。</span><span class="sxs-lookup"><span data-stu-id="35930-146">`pwzVersion` is not null and `pcchVersion` is null.</span></span><br /><br /> <span data-ttu-id="35930-147">\- または -</span><span class="sxs-lookup"><span data-stu-id="35930-147">-or-</span></span><br /><br /> <span data-ttu-id="35930-148">`pwzImageVersion` は null 以外で、`pcchImageVersion` は null です。</span><span class="sxs-lookup"><span data-stu-id="35930-148">`pwzImageVersion` is not null and `pcchImageVersion` is null.</span></span>|
|<span data-ttu-id="35930-149">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="35930-149">E_INVALIDARG</span></span>|<span data-ttu-id="35930-150">`dwPolicyFlags` は `METAHOST_POLICY_HIGHCOMPAT` を指定しません。</span><span class="sxs-lookup"><span data-stu-id="35930-150">`dwPolicyFlags` does not specify `METAHOST_POLICY_HIGHCOMPAT`.</span></span>|
|<span data-ttu-id="35930-151">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="35930-151">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="35930-152">`pwzVersion` に割り当てられたメモリが不十分です。</span><span class="sxs-lookup"><span data-stu-id="35930-152">The memory allocated to `pwzVersion` is inadequate.</span></span><br /><br /> <span data-ttu-id="35930-153">\- または -</span><span class="sxs-lookup"><span data-stu-id="35930-153">-or-</span></span><br /><br /> <span data-ttu-id="35930-154">`pwzImageVersion` に割り当てられたメモリが不十分です。</span><span class="sxs-lookup"><span data-stu-id="35930-154">The memory allocated to `pwzImageVersion` is inadequate.</span></span>|
|<span data-ttu-id="35930-155">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="35930-155">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="35930-156">`dwPolicyFlags` には METAHOST_POLICY_APPLY_UPGRADE_POLICY が含まれ、`pwzVersion` と `pcchVersion` はいずれも null です。</span><span class="sxs-lookup"><span data-stu-id="35930-156">`dwPolicyFlags` includes METAHOST_POLICY_APPLY_UPGRADE_POLICY, and both `pwzVersion` and `pcchVersion` are null.</span></span>|

## <a name="requirements"></a><span data-ttu-id="35930-157">要件</span><span class="sxs-lookup"><span data-stu-id="35930-157">Requirements</span></span>

<span data-ttu-id="35930-158">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35930-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="35930-159">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="35930-159">**Header:** MetaHost.h</span></span>

<span data-ttu-id="35930-160">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="35930-160">**Library:** Included as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="35930-161">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35930-161">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="35930-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="35930-162">See also</span></span>

- [<span data-ttu-id="35930-163">ICLRMetaHostPolicy インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35930-163">ICLRMetaHostPolicy Interface</span></span>](iclrmetahostpolicy-interface.md)
- [<span data-ttu-id="35930-164">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35930-164">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="35930-165">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35930-165">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="35930-166">ホスティング</span><span class="sxs-lookup"><span data-stu-id="35930-166">Hosting</span></span>](index.md)
