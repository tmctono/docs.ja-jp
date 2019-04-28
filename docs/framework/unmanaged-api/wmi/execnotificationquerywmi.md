---
title: ExecNotificationQueryWmi 関数 (アンマネージ API リファレンス)
description: ExecNotificationQueryWmi 関数は、イベントを受信するクエリを実行します。
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cac00ff96d0c7007bdd6135282c3f767217385e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935617"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="e45ce-103">ExecNotificationQueryWmi 関数</span><span class="sxs-lookup"><span data-stu-id="e45ce-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="e45ce-104">イベントを受信するクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e45ce-104">Executes a query to receive events.</span></span> <span data-ttu-id="e45ce-105">呼び出しが直ちに返され、呼び出し元は、到着すると、イベントの返された列挙子をポーリングします。</span><span class="sxs-lookup"><span data-stu-id="e45ce-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="e45ce-106">返された列挙子を解放するクエリをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="e45ce-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e45ce-107">構文</span><span class="sxs-lookup"><span data-stu-id="e45ce-107">Syntax</span></span>

```cpp
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
);
```

## <a name="parameters"></a><span data-ttu-id="e45ce-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e45ce-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="e45ce-109">[in]Windows の管理でサポートされる有効なクエリ言語を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="e45ce-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="e45ce-110">WMI クエリ言語の頭字語である"WQL"必要があります。</span><span class="sxs-lookup"><span data-stu-id="e45ce-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="e45ce-111">[in]クエリのテキスト。</span><span class="sxs-lookup"><span data-stu-id="e45ce-111">[in] The text of the query.</span></span> <span data-ttu-id="e45ce-112">このパラメーターを `null` とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e45ce-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="e45ce-113">[in]この関数の動作に影響する次の 2 つのフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="e45ce-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="e45ce-114">これらの値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="e45ce-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="e45ce-115">定数</span><span class="sxs-lookup"><span data-stu-id="e45ce-115">Constant</span></span> | <span data-ttu-id="e45ce-116">値</span><span class="sxs-lookup"><span data-stu-id="e45ce-116">Value</span></span>  | <span data-ttu-id="e45ce-117">説明</span><span class="sxs-lookup"><span data-stu-id="e45ce-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="e45ce-118">0x10</span><span class="sxs-lookup"><span data-stu-id="e45ce-118">0x10</span></span> | <span data-ttu-id="e45ce-119">フラグには、半同期的メソッドの呼び出しが行わします。</span><span class="sxs-lookup"><span data-stu-id="e45ce-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="e45ce-120">このフラグが設定されていない場合、呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="e45ce-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="e45ce-121">これは、イベントが継続的に、受信したため、ユーザーは、返された列挙子をポーリングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e45ce-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="e45ce-122">この呼び出しを無期限にブロックしているようにを不可能になります。</span><span class="sxs-lookup"><span data-stu-id="e45ce-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="e45ce-123">0x20</span><span class="sxs-lookup"><span data-stu-id="e45ce-123">0x20</span></span> | <span data-ttu-id="e45ce-124">関数は、順方向専用の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="e45ce-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="e45ce-125">呼び出しは許可されませんが、通常、順方向専用の列挙子は、高速と従来の列挙子より少ないメモリを使用して、[複製](clone.md)します。</span><span class="sxs-lookup"><span data-stu-id="e45ce-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="e45ce-126">[in]この値は、通常、`null`します。</span><span class="sxs-lookup"><span data-stu-id="e45ce-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="e45ce-127">ポインターは、それ以外の場合、 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)要求イベントを提供しているプロバイダーで使用できるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="e45ce-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="e45ce-128">[out]エラーが発生しない場合は、クエリの結果セットのインスタンスを取得する呼び出し元を許可する列挙子へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e45ce-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="e45ce-129">参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="e45ce-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="e45ce-130">[in]承認レベル。</span><span class="sxs-lookup"><span data-stu-id="e45ce-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="e45ce-131">[in]偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="e45ce-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="e45ce-132">[in]ポインター、 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)現在の名前空間を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e45ce-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="e45ce-133">[in]ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="e45ce-133">[in] The user name.</span></span> <span data-ttu-id="e45ce-134">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="e45ce-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="e45ce-135">[in]パスワードです。</span><span class="sxs-lookup"><span data-stu-id="e45ce-135">[in] The password.</span></span> <span data-ttu-id="e45ce-136">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="e45ce-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="e45ce-137">[in]ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="e45ce-137">[in] The domain name of the user.</span></span> <span data-ttu-id="e45ce-138">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="e45ce-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="e45ce-139">戻り値</span><span class="sxs-lookup"><span data-stu-id="e45ce-139">Return value</span></span>

<span data-ttu-id="e45ce-140">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="e45ce-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e45ce-141">定数</span><span class="sxs-lookup"><span data-stu-id="e45ce-141">Constant</span></span>  |<span data-ttu-id="e45ce-142">値</span><span class="sxs-lookup"><span data-stu-id="e45ce-142">Value</span></span>  |<span data-ttu-id="e45ce-143">説明</span><span class="sxs-lookup"><span data-stu-id="e45ce-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="e45ce-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="e45ce-144">0x80041003</span></span> | <span data-ttu-id="e45ce-145">ユーザーには、1 つ以上の関数が返すことができるクラスを表示するアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="e45ce-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="e45ce-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e45ce-146">0x80041001</span></span> | <span data-ttu-id="e45ce-147">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e45ce-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e45ce-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e45ce-148">0x80041008</span></span> | <span data-ttu-id="e45ce-149">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="e45ce-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="e45ce-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="e45ce-150">0x80041010</span></span> | <span data-ttu-id="e45ce-151">クエリでは、存在しないクラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e45ce-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="e45ce-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="e45ce-152">0x80042002</span></span> | <span data-ttu-id="e45ce-153">イベントの配信が多すぎるの精度が要求されています。</span><span class="sxs-lookup"><span data-stu-id="e45ce-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="e45ce-154">大規模なポーリングの許容範囲を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e45ce-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="e45ce-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="e45ce-155">0x80042001</span></span> | <span data-ttu-id="e45ce-156">クエリでは、Windows の管理を提供できるより多くの情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="e45ce-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="e45ce-157">これは、`HRESULT`イベント クエリの結果を名前空間のすべてのオブジェクトのポーリング要求したときに返されます。</span><span class="sxs-lookup"><span data-stu-id="e45ce-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="e45ce-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="e45ce-158">0x80041017</span></span> | <span data-ttu-id="e45ce-159">クエリでは、構文エラーがありました。</span><span class="sxs-lookup"><span data-stu-id="e45ce-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="e45ce-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="e45ce-160">0x80041018</span></span> | <span data-ttu-id="e45ce-161">要求されたクエリ言語がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e45ce-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="e45ce-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="e45ce-162">0x8004106c</span></span> | <span data-ttu-id="e45ce-163">クエリが複雑すぎます。</span><span class="sxs-lookup"><span data-stu-id="e45ce-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e45ce-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e45ce-164">0x80041006</span></span> | <span data-ttu-id="e45ce-165">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="e45ce-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="e45ce-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="e45ce-166">0x80041033</span></span> | <span data-ttu-id="e45ce-167">WMI は、おそらく停止および再起動されました。</span><span class="sxs-lookup"><span data-stu-id="e45ce-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="e45ce-168">呼び出す[ConnectServerWmi](connectserverwmi.md)もう一度です。</span><span class="sxs-lookup"><span data-stu-id="e45ce-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="e45ce-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="e45ce-169">0x80041015</span></span> | <span data-ttu-id="e45ce-170">現在のプロセスと WMI のリモート プロシージャ コール (RPC) リンクに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="e45ce-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="e45ce-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="e45ce-171">0x80041058</span></span> | <span data-ttu-id="e45ce-172">クエリを解析できません。</span><span class="sxs-lookup"><span data-stu-id="e45ce-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e45ce-173">0</span><span class="sxs-lookup"><span data-stu-id="e45ce-173">0</span></span> | <span data-ttu-id="e45ce-174">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="e45ce-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e45ce-175">Remarks</span><span class="sxs-lookup"><span data-stu-id="e45ce-175">Remarks</span></span>

<span data-ttu-id="e45ce-176">この関数の呼び出しをラップする、 [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery)メソッド。</span><span class="sxs-lookup"><span data-stu-id="e45ce-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="e45ce-177">呼び出し元が、返されたは定期的に、関数から制御が戻た後`ppEnum`オブジェクトを[次](next.md)関数を使用可能なイベントがあるを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e45ce-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="e45ce-178">数に制限は`AND`と`OR`WQL クエリで使用できるキーワードです。</span><span class="sxs-lookup"><span data-stu-id="e45ce-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="e45ce-179">WMI を返す可能性が多数の複雑なクエリで使用される WQL キーワード、 `WBEM_E_QUOTA_VIOLATION` (または 0x8004106c) としてのエラー コード、`HRESULT`値。</span><span class="sxs-lookup"><span data-stu-id="e45ce-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="e45ce-180">WQL キーワードの制限は、クエリの複雑な方法に依存します。</span><span class="sxs-lookup"><span data-stu-id="e45ce-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="e45ce-181">呼び出すことによって追加のエラー情報を取得するには、関数呼び出しに失敗した場合、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="e45ce-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="e45ce-182">必要条件</span><span class="sxs-lookup"><span data-stu-id="e45ce-182">Requirements</span></span>

<span data-ttu-id="e45ce-183">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e45ce-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="e45ce-184">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e45ce-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e45ce-185">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e45ce-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e45ce-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="e45ce-186">See also</span></span>

- [<span data-ttu-id="e45ce-187">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e45ce-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)