---
title: ExecQueryWmi 関数 (アンマネージ API リファレンス)
description: ExecQueryWmi 関数は、オブジェクトを取得するクエリを実行します。
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3c6ea58eca5ac635893a24b57ade261e04a69721
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130435"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="65bbb-103">ExecQueryWmi 関数</span><span class="sxs-lookup"><span data-stu-id="65bbb-103">ExecQueryWmi function</span></span>

<span data-ttu-id="65bbb-104">オブジェクトを取得するクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="65bbb-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="65bbb-105">構文</span><span class="sxs-lookup"><span data-stu-id="65bbb-105">Syntax</span></span>

```cpp
HRESULT ExecQueryWmi (
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

## <a name="parameters"></a><span data-ttu-id="65bbb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65bbb-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="65bbb-107">からWindows Management でサポートされている有効なクエリ言語を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="65bbb-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="65bbb-108">これは、WMI Query Language の頭字語である "WQL" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="65bbb-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="65bbb-109">からクエリのテキスト。</span><span class="sxs-lookup"><span data-stu-id="65bbb-109">[in] The text of the query.</span></span> <span data-ttu-id="65bbb-110">このパラメーターを `null` とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="65bbb-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="65bbb-111">からこの関数の動作に影響を与えるフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="65bbb-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="65bbb-112">次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="65bbb-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="65bbb-113">定数</span><span class="sxs-lookup"><span data-stu-id="65bbb-113">Constant</span></span> | <span data-ttu-id="65bbb-114">[値]</span><span class="sxs-lookup"><span data-stu-id="65bbb-114">Value</span></span>  | <span data-ttu-id="65bbb-115">説明</span><span class="sxs-lookup"><span data-stu-id="65bbb-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="65bbb-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="65bbb-116">0x20000</span></span> | <span data-ttu-id="65bbb-117">設定すると、関数は、現在の接続のロケールのローカライズされた名前空間に格納されている修正された修飾子を取得します。</span><span class="sxs-lookup"><span data-stu-id="65bbb-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="65bbb-118">設定されていない場合、関数は、イミディエイト名前空間に格納されている修飾子だけを取得します。</span><span class="sxs-lookup"><span data-stu-id="65bbb-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="65bbb-119">0x10</span><span class="sxs-lookup"><span data-stu-id="65bbb-119">0x10</span></span> | <span data-ttu-id="65bbb-120">このフラグにより、半同期呼び出しが発生します。</span><span class="sxs-lookup"><span data-stu-id="65bbb-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="65bbb-121">0x20</span><span class="sxs-lookup"><span data-stu-id="65bbb-121">0x20</span></span> | <span data-ttu-id="65bbb-122">関数は、順方向専用の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="65bbb-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="65bbb-123">通常、順方向専用の列挙子は、従来の列挙子よりも高速で使用されるメモリが少なくなりますが、[複製](clone.md)の呼び出しは許可されません。</span><span class="sxs-lookup"><span data-stu-id="65bbb-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="65bbb-124">0</span><span class="sxs-lookup"><span data-stu-id="65bbb-124">0</span></span> | <span data-ttu-id="65bbb-125">WMI は、列挙体が解放されるまで、そのオブジェクトへのポインターを保持します。</span><span class="sxs-lookup"><span data-stu-id="65bbb-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="65bbb-126">0x100</span><span class="sxs-lookup"><span data-stu-id="65bbb-126">0x100</span></span> | <span data-ttu-id="65bbb-127">返されたオブジェクトに十分な情報が含まれていることを確認して、 **__ PATH**、 **__RELPATH**、 **__ SERVER**などのシステムプロパティが `null`ないようにします。</span><span class="sxs-lookup"><span data-stu-id="65bbb-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="65bbb-128">2</span><span class="sxs-lookup"><span data-stu-id="65bbb-128">2</span></span> | <span data-ttu-id="65bbb-129">このフラグは、プロトタイプを行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="65bbb-129">This flag is used for prototyping.</span></span> <span data-ttu-id="65bbb-130">クエリは実行されず、代わりに通常の結果オブジェクトのように見えるオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="65bbb-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="65bbb-131">0x200</span><span class="sxs-lookup"><span data-stu-id="65bbb-131">0x200</span></span> | <span data-ttu-id="65bbb-132">親クラスまたはサブクラスに関係なく、指定されたクラスのプロバイダーに直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="65bbb-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="65bbb-133">最適なパフォーマンスを得るために、推奨されるフラグは `WBEM_FLAG_RETURN_IMMEDIATELY` と `WBEM_FLAG_FORWARD_ONLY` です。</span><span class="sxs-lookup"><span data-stu-id="65bbb-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="65bbb-134">から通常、この値は `null`です。</span><span class="sxs-lookup"><span data-stu-id="65bbb-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="65bbb-135">それ以外の場合は、要求されたクラスを提供しているプロバイダーが使用できる[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)インスタンスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="65bbb-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="65bbb-136">入出力エラーが発生しなかった場合、は、呼び出し元がクエリの結果セット内のインスタンスを取得できるようにする列挙子へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="65bbb-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="65bbb-137">クエリには、インスタンスがゼロの結果セットを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="65bbb-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="65bbb-138">詳細については、「[解説](#remarks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65bbb-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="65bbb-139">から承認レベル。</span><span class="sxs-lookup"><span data-stu-id="65bbb-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="65bbb-140">から偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="65bbb-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="65bbb-141">から現在の名前空間を表す[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="65bbb-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="65bbb-142">からユーザー名。</span><span class="sxs-lookup"><span data-stu-id="65bbb-142">[in] The user name.</span></span> <span data-ttu-id="65bbb-143">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65bbb-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="65bbb-144">からパスワード。</span><span class="sxs-lookup"><span data-stu-id="65bbb-144">[in] The password.</span></span> <span data-ttu-id="65bbb-145">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65bbb-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="65bbb-146">からユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="65bbb-146">[in] The domain name of the user.</span></span> <span data-ttu-id="65bbb-147">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65bbb-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="65bbb-148">戻り値</span><span class="sxs-lookup"><span data-stu-id="65bbb-148">Return value</span></span>

<span data-ttu-id="65bbb-149">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="65bbb-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="65bbb-150">定数</span><span class="sxs-lookup"><span data-stu-id="65bbb-150">Constant</span></span>  |<span data-ttu-id="65bbb-151">[値]</span><span class="sxs-lookup"><span data-stu-id="65bbb-151">Value</span></span>  |<span data-ttu-id="65bbb-152">説明</span><span class="sxs-lookup"><span data-stu-id="65bbb-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="65bbb-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="65bbb-153">0x80041003</span></span> | <span data-ttu-id="65bbb-154">関数が返すことのできる1つ以上のクラスを表示するアクセス許可がユーザーにありません。</span><span class="sxs-lookup"><span data-stu-id="65bbb-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="65bbb-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="65bbb-155">0x80041001</span></span> | <span data-ttu-id="65bbb-156">特定できないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="65bbb-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="65bbb-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="65bbb-157">0x80041008</span></span> | <span data-ttu-id="65bbb-158">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="65bbb-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="65bbb-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="65bbb-159">0x80041017</span></span> | <span data-ttu-id="65bbb-160">クエリで構文エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="65bbb-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="65bbb-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="65bbb-161">0x80041018</span></span> | <span data-ttu-id="65bbb-162">要求されたクエリ言語はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65bbb-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="65bbb-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="65bbb-163">0x8004106c</span></span> | <span data-ttu-id="65bbb-164">クエリが複雑すぎます。</span><span class="sxs-lookup"><span data-stu-id="65bbb-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="65bbb-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="65bbb-165">0x80041006</span></span> | <span data-ttu-id="65bbb-166">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="65bbb-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="65bbb-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="65bbb-167">0x80041033</span></span> | <span data-ttu-id="65bbb-168">WMI が停止し、再起動されたことがあります。</span><span class="sxs-lookup"><span data-stu-id="65bbb-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="65bbb-169">[Connectserverwmi](connectserverwmi.md)を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="65bbb-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="65bbb-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="65bbb-170">0x80041015</span></span> | <span data-ttu-id="65bbb-171">現在のプロセスと WMI の間のリモートプロシージャコール (RPC) リンクが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="65bbb-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="65bbb-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="65bbb-172">0x80041002</span></span> | <span data-ttu-id="65bbb-173">このクエリでは、存在しないクラスが指定されています。</span><span class="sxs-lookup"><span data-stu-id="65bbb-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="65bbb-174">0</span><span class="sxs-lookup"><span data-stu-id="65bbb-174">0</span></span> | <span data-ttu-id="65bbb-175">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="65bbb-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="65bbb-176">Remarks</span><span class="sxs-lookup"><span data-stu-id="65bbb-176">Remarks</span></span>

<span data-ttu-id="65bbb-177">この関数は、 [IWbemServices:: ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="65bbb-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="65bbb-178">この関数は、`strQuery` パラメーターで指定されたクエリを処理し、呼び出し元がクエリ結果にアクセスするための列挙子を作成します。</span><span class="sxs-lookup"><span data-stu-id="65bbb-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="65bbb-179">列挙子は、 [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)インターフェイスへのポインターです。クエリの結果は、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インターフェイスを通じて使用できるクラスオブジェクトのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="65bbb-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="65bbb-180">WQL クエリで使用できる `AND` および `OR` キーワードの数には制限があります。</span><span class="sxs-lookup"><span data-stu-id="65bbb-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="65bbb-181">複雑なクエリで使用される WQL キーワードの数が多いと、WMI が `WBEM_E_QUOTA_VIOLATION` (または 0x8004106c) エラーコードを `HRESULT` 値として返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="65bbb-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="65bbb-182">WQL キーワードの制限は、クエリの複雑さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="65bbb-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="65bbb-183">関数呼び出しが失敗した場合は、 [GetErrorInfo](geterrorinfo.md)関数を呼び出して追加のエラー情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="65bbb-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="65bbb-184">［要件］</span><span class="sxs-lookup"><span data-stu-id="65bbb-184">Requirements</span></span>

<span data-ttu-id="65bbb-185">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65bbb-185">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="65bbb-186">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="65bbb-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="65bbb-187">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="65bbb-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="65bbb-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="65bbb-188">See also</span></span>

- [<span data-ttu-id="65bbb-189">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="65bbb-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
