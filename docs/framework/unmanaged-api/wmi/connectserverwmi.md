---
title: ConnectServerWmi 関数 (アンマネージ API リファレンス)
description: ConnectServerWmi 関数は、DCOM を使用して WMI 名前空間への接続を作成します。
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
ms.openlocfilehash: 25a73060ed242fd0e77042cd0ea9618b9b27250f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128691"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="c349c-103">ConnectServerWmi 関数</span><span class="sxs-lookup"><span data-stu-id="c349c-103">ConnectServerWmi function</span></span>

<span data-ttu-id="c349c-104">指定したコンピューターにある WMI 名前空間との接続が DCOM 経由で作成されます。</span><span class="sxs-lookup"><span data-stu-id="c349c-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c349c-105">構文</span><span class="sxs-lookup"><span data-stu-id="c349c-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="c349c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c349c-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="c349c-107">から正しい WMI 名前空間のオブジェクトパスを含む有効な `BSTR` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c349c-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="c349c-108">詳細については、「[解説](#remarks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c349c-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="c349c-109">からユーザー名を含む有効な `BSTR` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c349c-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="c349c-110">`null` 値は、現在のセキュリティコンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="c349c-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="c349c-111">ユーザーが現在のドメインとは異なるドメインにある場合、`strUser` には、円記号で区切られたドメインとユーザー名を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="c349c-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="c349c-112">`strUser` は、`userName@domainName`などのユーザープリンシパル名 (UPN) 形式で指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c349c-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="c349c-113">詳細については、「[解説](#remarks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c349c-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="c349c-114">からパスワードを格納している有効な `BSTR` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c349c-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="c349c-115">現在のセキュリティコンテキストを示す `null`。</span><span class="sxs-lookup"><span data-stu-id="c349c-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="c349c-116">空の文字列 ("") は、長さ0の有効なパスワードを示します。</span><span class="sxs-lookup"><span data-stu-id="c349c-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="c349c-117">から情報取得の正しいロケールを示す有効な `BSTR` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c349c-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="c349c-118">Microsoft ロケール識別子の場合、文字列の形式は "MS\_*xxx*" です。ここで、 *xxx*はロケール識別子 (LCID) を示す16進数形式の文字列です。</span><span class="sxs-lookup"><span data-stu-id="c349c-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="c349c-119">無効なロケールが指定されている場合、メソッドは、サーバーの既定のロケールが代わりに使用される Windows 7 以外の `WBEM_E_INVALID_PARAMETER` を返します。</span><span class="sxs-lookup"><span data-stu-id="c349c-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="c349c-120">' Null1 ' の場合、現在のロケールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c349c-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="c349c-121">から`ConnectServerWmi` メソッドに渡すフラグ。</span><span class="sxs-lookup"><span data-stu-id="c349c-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="c349c-122">このパラメーターにゼロ (0) を指定すると、サーバーへの接続が確立された後にのみを返す `ConnectServerWmi` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c349c-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="c349c-123">これにより、サーバーが破損した場合にアプリケーションが無期限に応答しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c349c-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="c349c-124">その他の有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c349c-124">The other valid values are:</span></span>

| <span data-ttu-id="c349c-125">定数</span><span class="sxs-lookup"><span data-stu-id="c349c-125">Constant</span></span>  | <span data-ttu-id="c349c-126">[値]</span><span class="sxs-lookup"><span data-stu-id="c349c-126">Value</span></span>  | <span data-ttu-id="c349c-127">説明</span><span class="sxs-lookup"><span data-stu-id="c349c-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="c349c-128">0x40</span><span class="sxs-lookup"><span data-stu-id="c349c-128">0x40</span></span> | <span data-ttu-id="c349c-129">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="c349c-129">Reserved for internal use.</span></span> <span data-ttu-id="c349c-130">使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c349c-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="c349c-131">0x80</span><span class="sxs-lookup"><span data-stu-id="c349c-131">0x80</span></span> | <span data-ttu-id="c349c-132">`ConnectServerWmi` は2分以内で返されます。</span><span class="sxs-lookup"><span data-stu-id="c349c-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="c349c-133">からユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="c349c-133">[in] The domain name of the user.</span></span> <span data-ttu-id="c349c-134">次の値のいずれかを取ります。</span><span class="sxs-lookup"><span data-stu-id="c349c-134">It can have the following values:</span></span>

| <span data-ttu-id="c349c-135">[値]</span><span class="sxs-lookup"><span data-stu-id="c349c-135">Value</span></span> | <span data-ttu-id="c349c-136">説明</span><span class="sxs-lookup"><span data-stu-id="c349c-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="c349c-137">空白</span><span class="sxs-lookup"><span data-stu-id="c349c-137">blank</span></span> | <span data-ttu-id="c349c-138">NTLM 認証が使用され、現在のユーザーの NTLM ドメインが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c349c-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="c349c-139">`strUser` ドメイン (推奨される場所) を指定する場合は、ここで指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="c349c-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="c349c-140">この関数は、両方のパラメーターでドメインを指定した場合に `WBEM_E_INVALID_PARAMETER` を返します。</span><span class="sxs-lookup"><span data-stu-id="c349c-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="c349c-141">Kerberos:*プリンシパル名*</span><span class="sxs-lookup"><span data-stu-id="c349c-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="c349c-142">Kerberos 認証が使用され、このパラメーターには Kerberos プリンシパル名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c349c-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="c349c-143">NTLMDOMAIN:*ドメイン名*</span><span class="sxs-lookup"><span data-stu-id="c349c-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="c349c-144">NT LAN Manager 認証が使用され、このパラメーターには NTLM ドメイン名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c349c-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="c349c-145">から通常、このパラメーターは `null`です。</span><span class="sxs-lookup"><span data-stu-id="c349c-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="c349c-146">それ以外の場合は、1つまたは複数の動的クラスプロバイダーが必要とする[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)オブジェクトへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="c349c-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="c349c-147">入出力関数から制御が戻るときに、指定した名前空間にバインドされている[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)オブジェクトへのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c349c-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="c349c-148">エラーが発生したときに `null` を指すように設定されています。</span><span class="sxs-lookup"><span data-stu-id="c349c-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="c349c-149">から偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="c349c-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="c349c-150">から承認レベル。</span><span class="sxs-lookup"><span data-stu-id="c349c-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="c349c-151">戻り値</span><span class="sxs-lookup"><span data-stu-id="c349c-151">Return value</span></span>

<span data-ttu-id="c349c-152">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="c349c-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c349c-153">定数</span><span class="sxs-lookup"><span data-stu-id="c349c-153">Constant</span></span>  |<span data-ttu-id="c349c-154">[値]</span><span class="sxs-lookup"><span data-stu-id="c349c-154">Value</span></span>  |<span data-ttu-id="c349c-155">説明</span><span class="sxs-lookup"><span data-stu-id="c349c-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="c349c-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c349c-156">0x80041001</span></span> | <span data-ttu-id="c349c-157">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c349c-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c349c-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c349c-158">0x80041008</span></span> | <span data-ttu-id="c349c-159">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="c349c-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c349c-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c349c-160">0x80041006</span></span> | <span data-ttu-id="c349c-161">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="c349c-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c349c-162">0</span><span class="sxs-lookup"><span data-stu-id="c349c-162">0</span></span> | <span data-ttu-id="c349c-163">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="c349c-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="c349c-164">Remarks</span><span class="sxs-lookup"><span data-stu-id="c349c-164">Remarks</span></span>

<span data-ttu-id="c349c-165">この関数は、 [IWbemLocator:: ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="c349c-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="c349c-166">既定の名前空間へのローカルアクセスの場合、`strNetworkResource` には単純なオブジェクトパス ("root\default" または "\\.\root\default") を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c349c-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="c349c-167">COM または Microsoft と互換性のあるネットワークを使用してリモートコンピューター上の既定の名前空間にアクセスするには、"\\myserver\root\default" というコンピューター名を含めます。</span><span class="sxs-lookup"><span data-stu-id="c349c-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="c349c-168">コンピューター名には、DNS 名または IP アドレスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c349c-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="c349c-169">`ConnectServerWmi` 関数は、ipv6 アドレスを使用して IPv6 を実行しているコンピューターに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="c349c-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="c349c-170">`strUser` を空の文字列にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c349c-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="c349c-171">ドメインが `strAuthority`で指定されている場合は、`strUser`に含めないようにする必要があります。そうしないと、関数は `WBEM_E_INVALID_PARAMETER`を返します。</span><span class="sxs-lookup"><span data-stu-id="c349c-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="c349c-172">［要件］</span><span class="sxs-lookup"><span data-stu-id="c349c-172">Requirements</span></span>

 <span data-ttu-id="c349c-173">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c349c-173">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="c349c-174">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="c349c-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="c349c-175">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c349c-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c349c-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="c349c-176">See also</span></span>

- [<span data-ttu-id="c349c-177">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c349c-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
