---
title: ExecNotificationQueryWmi 関数 (アンマネージ API リファレンス)
description: ExecNotificationQueryWmi 関数は、イベントを受信するためのクエリを実行します。
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
ms.openlocfilehash: 5cfe54c7c9b7ae707b2d3591afbd830bac171f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798645"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="f9815-103">ExecNotificationQueryWmi 関数</span><span class="sxs-lookup"><span data-stu-id="f9815-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="f9815-104">イベントを受信するクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f9815-104">Executes a query to receive events.</span></span> <span data-ttu-id="f9815-105">呼び出しはすぐに返されます。呼び出し元は、返されたイベントの列挙子をポーリングできます。</span><span class="sxs-lookup"><span data-stu-id="f9815-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="f9815-106">返された列挙子を解放すると、クエリが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="f9815-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f9815-107">構文</span><span class="sxs-lookup"><span data-stu-id="f9815-107">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="f9815-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9815-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="f9815-109">からWindows Management でサポートされている有効なクエリ言語を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="f9815-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="f9815-110">これは、WMI Query Language の頭字語である "WQL" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9815-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="f9815-111">からクエリのテキスト。</span><span class="sxs-lookup"><span data-stu-id="f9815-111">[in] The text of the query.</span></span> <span data-ttu-id="f9815-112">このパラメーターを `null` とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f9815-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="f9815-113">からこの関数の動作に影響を与える、次の2つのフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="f9815-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="f9815-114">これらの値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9815-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="f9815-115">定数</span><span class="sxs-lookup"><span data-stu-id="f9815-115">Constant</span></span> | <span data-ttu-id="f9815-116">Value</span><span class="sxs-lookup"><span data-stu-id="f9815-116">Value</span></span>  | <span data-ttu-id="f9815-117">説明</span><span class="sxs-lookup"><span data-stu-id="f9815-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="f9815-118">0x10</span><span class="sxs-lookup"><span data-stu-id="f9815-118">0x10</span></span> | <span data-ttu-id="f9815-119">このフラグにより、半同期呼び出しが発生します。</span><span class="sxs-lookup"><span data-stu-id="f9815-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="f9815-120">このフラグが設定されていない場合、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f9815-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="f9815-121">これは、イベントが連続して受信されるためです。これは、ユーザーが返された列挙子をポーリングする必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f9815-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="f9815-122">この呼び出しを無制限にブロックすると、そのようなことは不可能になります。</span><span class="sxs-lookup"><span data-stu-id="f9815-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="f9815-123">0x20</span><span class="sxs-lookup"><span data-stu-id="f9815-123">0x20</span></span> | <span data-ttu-id="f9815-124">関数は、順方向専用の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="f9815-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="f9815-125">通常、順方向専用の列挙子は、従来の列挙子よりも高速で使用されるメモリが少なくなりますが、[複製](clone.md)の呼び出しは許可されません。</span><span class="sxs-lookup"><span data-stu-id="f9815-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="f9815-126">から通常、この値は`null`です。</span><span class="sxs-lookup"><span data-stu-id="f9815-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="f9815-127">それ以外の場合は、要求されたイベントを提供しているプロバイダーが使用できる[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)インスタンスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="f9815-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="f9815-128">入出力エラーが発生しなかった場合、は、呼び出し元がクエリの結果セット内のインスタンスを取得できるようにする列挙子へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f9815-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="f9815-129">詳細については、「[解説](#remarks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9815-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="f9815-130">から承認レベル。</span><span class="sxs-lookup"><span data-stu-id="f9815-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="f9815-131">から偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="f9815-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="f9815-132">から現在の名前空間を表す[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f9815-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="f9815-133">からユーザー名。</span><span class="sxs-lookup"><span data-stu-id="f9815-133">[in] The user name.</span></span> <span data-ttu-id="f9815-134">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9815-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="f9815-135">からパスワード。</span><span class="sxs-lookup"><span data-stu-id="f9815-135">[in] The password.</span></span> <span data-ttu-id="f9815-136">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9815-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="f9815-137">からユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="f9815-137">[in] The domain name of the user.</span></span> <span data-ttu-id="f9815-138">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9815-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="f9815-139">戻り値</span><span class="sxs-lookup"><span data-stu-id="f9815-139">Return value</span></span>

<span data-ttu-id="f9815-140">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9815-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f9815-141">定数</span><span class="sxs-lookup"><span data-stu-id="f9815-141">Constant</span></span>  |<span data-ttu-id="f9815-142">Value</span><span class="sxs-lookup"><span data-stu-id="f9815-142">Value</span></span>  |<span data-ttu-id="f9815-143">説明</span><span class="sxs-lookup"><span data-stu-id="f9815-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="f9815-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="f9815-144">0x80041003</span></span> | <span data-ttu-id="f9815-145">関数が返すことのできる1つ以上のクラスを表示するアクセス許可がユーザーにありません。</span><span class="sxs-lookup"><span data-stu-id="f9815-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="f9815-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f9815-146">0x80041001</span></span> | <span data-ttu-id="f9815-147">特定できないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f9815-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f9815-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f9815-148">0x80041008</span></span> | <span data-ttu-id="f9815-149">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="f9815-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="f9815-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="f9815-150">0x80041010</span></span> | <span data-ttu-id="f9815-151">このクエリでは、存在しないクラスが指定されています。</span><span class="sxs-lookup"><span data-stu-id="f9815-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="f9815-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="f9815-152">0x80042002</span></span> | <span data-ttu-id="f9815-153">要求されたイベント配信の精度が大きすぎます。</span><span class="sxs-lookup"><span data-stu-id="f9815-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="f9815-154">より大きなポーリング許容範囲を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9815-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="f9815-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="f9815-155">0x80042001</span></span> | <span data-ttu-id="f9815-156">このクエリでは、Windows Management で提供されるよりも多くの情報が要求されます。</span><span class="sxs-lookup"><span data-stu-id="f9815-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="f9815-157">これ`HRESULT`は、イベントクエリによって名前空間内のすべてのオブジェクトをポーリングする要求が発生した場合に返されます。</span><span class="sxs-lookup"><span data-stu-id="f9815-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="f9815-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="f9815-158">0x80041017</span></span> | <span data-ttu-id="f9815-159">クエリで構文エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f9815-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="f9815-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="f9815-160">0x80041018</span></span> | <span data-ttu-id="f9815-161">要求されたクエリ言語はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f9815-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="f9815-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="f9815-162">0x8004106c</span></span> | <span data-ttu-id="f9815-163">クエリが複雑すぎます。</span><span class="sxs-lookup"><span data-stu-id="f9815-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f9815-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f9815-164">0x80041006</span></span> | <span data-ttu-id="f9815-165">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="f9815-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="f9815-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="f9815-166">0x80041033</span></span> | <span data-ttu-id="f9815-167">WMI が停止し、再起動されたことがあります。</span><span class="sxs-lookup"><span data-stu-id="f9815-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="f9815-168">[Connectserverwmi](connectserverwmi.md)を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f9815-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="f9815-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="f9815-169">0x80041015</span></span> | <span data-ttu-id="f9815-170">現在のプロセスと WMI の間のリモートプロシージャコール (RPC) リンクが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f9815-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="f9815-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="f9815-171">0x80041058</span></span> | <span data-ttu-id="f9815-172">クエリを解析できません。</span><span class="sxs-lookup"><span data-stu-id="f9815-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f9815-173">0</span><span class="sxs-lookup"><span data-stu-id="f9815-173">0</span></span> | <span data-ttu-id="f9815-174">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="f9815-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="f9815-175">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9815-175">Remarks</span></span>

<span data-ttu-id="f9815-176">この関数は、 [IWbemServices:: ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="f9815-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="f9815-177">関数が返された後、呼び出し元は、 `ppEnum`返されたオブジェクトを定期的に[次](next.md)の関数に渡して、使用可能なイベントがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9815-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="f9815-178">WQL クエリで使用できるキーワードと`AND` `OR`キーワードの数には制限があります。</span><span class="sxs-lookup"><span data-stu-id="f9815-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="f9815-179">複雑なクエリで使用される WQL キーワードの数が多いと、WMI `WBEM_E_QUOTA_VIOLATION`が (または 0x8004106c) エラーコード`HRESULT`を値として返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="f9815-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="f9815-180">WQL キーワードの制限は、クエリの複雑さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f9815-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="f9815-181">関数呼び出しが失敗した場合は、 [GetErrorInfo](geterrorinfo.md)関数を呼び出して追加のエラー情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f9815-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="f9815-182">必要条件</span><span class="sxs-lookup"><span data-stu-id="f9815-182">Requirements</span></span>

<span data-ttu-id="f9815-183">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9815-183">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f9815-184">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="f9815-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="f9815-185">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f9815-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f9815-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9815-186">See also</span></span>

- [<span data-ttu-id="f9815-187">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f9815-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
