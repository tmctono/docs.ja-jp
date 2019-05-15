---
title: ConnectServerWmi 関数 (アンマネージ API リファレンス)
description: ConnectServerWmi 関数では、DCOM を使用して、WMI 名前空間への接続を作成します。
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e88129f737ee493432d06acc6ad45f8653dd1eb4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636769"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="41fa9-103">ConnectServerWmi 関数</span><span class="sxs-lookup"><span data-stu-id="41fa9-103">ConnectServerWmi function</span></span>

<span data-ttu-id="41fa9-104">指定したコンピューターにある WMI 名前空間との接続が DCOM 経由で作成されます。</span><span class="sxs-lookup"><span data-stu-id="41fa9-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="41fa9-105">構文</span><span class="sxs-lookup"><span data-stu-id="41fa9-105">Syntax</span></span>

```cpp
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel,
   [in] DWORD              authLevel
);
```

## <a name="parameters"></a><span data-ttu-id="41fa9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41fa9-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="41fa9-107">[in]有効なポインター`BSTR`正しい WMI 名前空間のオブジェクトのパスを格納しています。</span><span class="sxs-lookup"><span data-stu-id="41fa9-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="41fa9-108">参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="41fa9-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="41fa9-109">[in]有効なへのポインター`BSTR`ユーザー名を格納しています。</span><span class="sxs-lookup"><span data-stu-id="41fa9-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="41fa9-110">A`null`値が現在のセキュリティ コンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="41fa9-111">場合、ユーザーは、現在の 1 つの異なるドメインから`strUser`円記号で区切られたドメインとユーザー名を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="41fa9-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="41fa9-112">`strUser` できるようにユーザー プリンシパル名 (UPN) 形式でも`userName@domainName`します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="41fa9-113">参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="41fa9-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="41fa9-114">[in]有効なへのポインター`BSTR`パスワードを格納しています。</span><span class="sxs-lookup"><span data-stu-id="41fa9-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="41fa9-115">A`null`現在のセキュリティ コンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="41fa9-116">空の文字列 ("")、有効な長さ 0 のパスワードを示します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="41fa9-117">[in]有効なへのポインター`BSTR`情報の取得を適切なロケールを示します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="41fa9-118">マイクロソフト ロケールの識別子、文字列の形式は"MS\_*xxx*"ここで、 *xxx*文字列がロケール識別子 (LCID) を示す 16 進数形式です。</span><span class="sxs-lookup"><span data-stu-id="41fa9-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="41fa9-119">無効なロケールが指定されているかどうか、メソッドを返します`WBEM_E_INVALID_PARAMETER`Windows 7、サーバーの既定のロケールが代わりに使用される場合は除きます。</span><span class="sxs-lookup"><span data-stu-id="41fa9-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="41fa9-120">場合 ' null 1、現在のロケールを使用します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="41fa9-121">[in]渡すフラグ、`ConnectServerWmi`メソッド。</span><span class="sxs-lookup"><span data-stu-id="41fa9-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="41fa9-122">このパラメーターにゼロ (0) の値の結果への呼び出しで`ConnectServerWmi`サーバーへの接続が確立された後にのみを返します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="41fa9-123">これは、結果、応答していない無期限に、サーバーが切断されたかどうか、アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="41fa9-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="41fa9-124">その他の有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="41fa9-124">The other valid values are:</span></span>

| <span data-ttu-id="41fa9-125">定数</span><span class="sxs-lookup"><span data-stu-id="41fa9-125">Constant</span></span>  | <span data-ttu-id="41fa9-126">値</span><span class="sxs-lookup"><span data-stu-id="41fa9-126">Value</span></span>  | <span data-ttu-id="41fa9-127">説明</span><span class="sxs-lookup"><span data-stu-id="41fa9-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="41fa9-128">0x40</span><span class="sxs-lookup"><span data-stu-id="41fa9-128">0x40</span></span> | <span data-ttu-id="41fa9-129">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="41fa9-129">Reserved for internal use.</span></span> <span data-ttu-id="41fa9-130">使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="41fa9-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="41fa9-131">0x80</span><span class="sxs-lookup"><span data-stu-id="41fa9-131">0x80</span></span> | <span data-ttu-id="41fa9-132">`ConnectServerWmi` 2 分以内に返されます。</span><span class="sxs-lookup"><span data-stu-id="41fa9-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="41fa9-133">[in]ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="41fa9-133">[in] The domain name of the user.</span></span> <span data-ttu-id="41fa9-134">次の値のいずれかを取ります。</span><span class="sxs-lookup"><span data-stu-id="41fa9-134">It can have the following values:</span></span>

| <span data-ttu-id="41fa9-135">値</span><span class="sxs-lookup"><span data-stu-id="41fa9-135">Value</span></span> | <span data-ttu-id="41fa9-136">説明</span><span class="sxs-lookup"><span data-stu-id="41fa9-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="41fa9-137">空白</span><span class="sxs-lookup"><span data-stu-id="41fa9-137">blank</span></span> | <span data-ttu-id="41fa9-138">NTLM 認証を使用して、現在のユーザーの NTLM ドメインが使用されます。</span><span class="sxs-lookup"><span data-stu-id="41fa9-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="41fa9-139">場合`strUser`ドメイン (推奨される場所) を指定します。 ここで指定しない必要がありますに。</span><span class="sxs-lookup"><span data-stu-id="41fa9-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="41fa9-140">関数を返します`WBEM_E_INVALID_PARAMETER`両方のパラメーターでドメインを指定する場合。</span><span class="sxs-lookup"><span data-stu-id="41fa9-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="41fa9-141">Kerberos:*プリンシパル名*</span><span class="sxs-lookup"><span data-stu-id="41fa9-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="41fa9-142">Kerberos 認証を使用して、このパラメーターには、Kerberos プリンシパル名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41fa9-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="41fa9-143">NTLMDOMAIN:*ドメイン名*</span><span class="sxs-lookup"><span data-stu-id="41fa9-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="41fa9-144">NT LAN Manager 認証を使用して、このパラメーターには、NTLM ドメイン名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41fa9-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="41fa9-145">[in]このパラメーターは、通常、`null`します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="41fa9-146">ポインターは、それ以外の場合、 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)オブジェクトが 1 つまたは複数の動的クラス プロバイダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="41fa9-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="41fa9-147">[out]ポインターを受け取る関数が戻るとき、 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)オブジェクトを指定した名前空間にバインドします。</span><span class="sxs-lookup"><span data-stu-id="41fa9-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="41fa9-148">をポイントに設定されている`null`エラーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="41fa9-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="41fa9-149">[in]偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="41fa9-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="41fa9-150">[in]承認レベル。</span><span class="sxs-lookup"><span data-stu-id="41fa9-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="41fa9-151">戻り値</span><span class="sxs-lookup"><span data-stu-id="41fa9-151">Return value</span></span>

<span data-ttu-id="41fa9-152">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="41fa9-153">定数</span><span class="sxs-lookup"><span data-stu-id="41fa9-153">Constant</span></span>  |<span data-ttu-id="41fa9-154">値</span><span class="sxs-lookup"><span data-stu-id="41fa9-154">Value</span></span>  |<span data-ttu-id="41fa9-155">説明</span><span class="sxs-lookup"><span data-stu-id="41fa9-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="41fa9-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="41fa9-156">0x80041001</span></span> | <span data-ttu-id="41fa9-157">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="41fa9-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="41fa9-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="41fa9-158">0x80041008</span></span> | <span data-ttu-id="41fa9-159">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="41fa9-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="41fa9-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="41fa9-160">0x80041006</span></span> | <span data-ttu-id="41fa9-161">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="41fa9-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="41fa9-162">0</span><span class="sxs-lookup"><span data-stu-id="41fa9-162">0</span></span> | <span data-ttu-id="41fa9-163">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="41fa9-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="41fa9-164">Remarks</span><span class="sxs-lookup"><span data-stu-id="41fa9-164">Remarks</span></span>

<span data-ttu-id="41fa9-165">この関数の呼び出しをラップする、 [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver)メソッド。</span><span class="sxs-lookup"><span data-stu-id="41fa9-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="41fa9-166">既定の名前空間へのローカル アクセスの`strNetworkResource`簡単なオブジェクト パスを指定することができます。"root \default"または"\\.\root\default"。</span><span class="sxs-lookup"><span data-stu-id="41fa9-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="41fa9-167">リモート コンピューター上の既定の名前空間にアクセスするため、COM や Microsoft と互換性のあるネットワークを使用して、コンピューター名を含める:"\\myserver\root\default"。</span><span class="sxs-lookup"><span data-stu-id="41fa9-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="41fa9-168">コンピューター名は、DNS 名または IP アドレスを使用することも。</span><span class="sxs-lookup"><span data-stu-id="41fa9-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="41fa9-169">`ConnectServerWmi`関数は IPv6 を実行しているコンピューターにも接続できる IPv6 アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="41fa9-170">`strUser` 空の文字列にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="41fa9-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="41fa9-171">ドメインがで指定されている場合`strAuthority`、いないも含める必要がありますで`strUser`、関数を返しますまたは`WBEM_E_INVALID_PARAMETER`します。</span><span class="sxs-lookup"><span data-stu-id="41fa9-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="41fa9-172">必要条件</span><span class="sxs-lookup"><span data-stu-id="41fa9-172">Requirements</span></span>

 <span data-ttu-id="41fa9-173">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41fa9-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="41fa9-174">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="41fa9-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="41fa9-175">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="41fa9-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="41fa9-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="41fa9-176">See also</span></span>

- [<span data-ttu-id="41fa9-177">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="41fa9-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
