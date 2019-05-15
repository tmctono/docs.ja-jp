---
title: CreateInstanceEnumWmi 関数 (アンマネージ API リファレンス)
description: CreateInstanceEnumWmi 関数は、選択条件を満たす、指定されたクラスのインスタンスを含む列挙子を返します。
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db325296d85dc6d4780583731a6cab10fb884fd1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636482"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="3bcbc-103">CreateInstanceEnumWmi 関数</span><span class="sxs-lookup"><span data-stu-id="3bcbc-103">CreateInstanceEnumWmi function</span></span>

<span data-ttu-id="3bcbc-104">指定したクラスのインスタンスの中から指定した選択条件を満たすものを返す列挙子が返されます。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3bcbc-105">構文</span><span class="sxs-lookup"><span data-stu-id="3bcbc-105">Syntax</span></span>

```cpp
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
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

## <a name="parameters"></a><span data-ttu-id="3bcbc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3bcbc-106">Parameters</span></span>

`strFilter`\
<span data-ttu-id="3bcbc-107">[in]インスタンスが必要なクラスの名前。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="3bcbc-108">このパラメーターを `null` とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-108">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="3bcbc-109">[in]この関数の動作に影響するフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="3bcbc-110">次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3bcbc-111">定数</span><span class="sxs-lookup"><span data-stu-id="3bcbc-111">Constant</span></span>  |<span data-ttu-id="3bcbc-112">値</span><span class="sxs-lookup"><span data-stu-id="3bcbc-112">Value</span></span>  |<span data-ttu-id="3bcbc-113">説明</span><span class="sxs-lookup"><span data-stu-id="3bcbc-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="3bcbc-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="3bcbc-114">0x20000</span></span> | <span data-ttu-id="3bcbc-115">セット、関数は、現在の接続のロケールのローカライズされた名前空間に格納されている修正済みの修飾子を取得します。 場合、</span><span class="sxs-lookup"><span data-stu-id="3bcbc-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="3bcbc-116">指定しない場合、セット、関数は、即時の名前空間に格納されている修飾子のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="3bcbc-117">0</span><span class="sxs-lookup"><span data-stu-id="3bcbc-117">0</span></span> | <span data-ttu-id="3bcbc-118">列挙体には、階層内のすべてのサブクラスとこれが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="3bcbc-119">1</span><span class="sxs-lookup"><span data-stu-id="3bcbc-119">1</span></span> | <span data-ttu-id="3bcbc-120">列挙体は、このクラスの純粋なインスタンスのみが含まれていますおよび、このクラスにないプロパティが指定のサブクラスのすべてのインスタンスを除外します。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="3bcbc-121">0x10</span><span class="sxs-lookup"><span data-stu-id="3bcbc-121">0x10</span></span> | <span data-ttu-id="3bcbc-122">フラグには、半同期的メソッドの呼び出しが行わします。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="3bcbc-123">0x20</span><span class="sxs-lookup"><span data-stu-id="3bcbc-123">0x20</span></span> | <span data-ttu-id="3bcbc-124">関数は、順方向専用の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="3bcbc-125">呼び出しは許可されませんが、通常、順方向専用の列挙子は、高速と従来の列挙子より少ないメモリを使用して、[複製](clone.md)します。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="3bcbc-126">0</span><span class="sxs-lookup"><span data-stu-id="3bcbc-126">0</span></span> | <span data-ttu-id="3bcbc-127">WMI は、リリースされるまでに、列挙内のオブジェクトへのポインターを保持します。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-127">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="3bcbc-128">推奨されるフラグは`WBEM_FLAG_RETURN_IMMEDIATELY`と`WBEM_FLAG_FORWARD_ONLY`最適なパフォーマンス。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="3bcbc-129">[in]この値は、通常、`null`します。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="3bcbc-130">ポインターは、それ以外の場合、 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)インスタンスを要求されたインスタンスを提供しているプロバイダーによって使用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-130">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`\
<span data-ttu-id="3bcbc-131">[out]列挙子へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="3bcbc-132">[in]承認レベル。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-132">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="3bcbc-133">[in]偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-133">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="3bcbc-134">[in]ポインター、 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)現在の名前空間を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-134">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="3bcbc-135">[in]ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-135">[in] The user name.</span></span> <span data-ttu-id="3bcbc-136">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="3bcbc-137">[in]パスワードです。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-137">[in] The password.</span></span> <span data-ttu-id="3bcbc-138">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="3bcbc-139">[in]ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-139">[in] The domain name of the user.</span></span> <span data-ttu-id="3bcbc-140">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="3bcbc-141">戻り値</span><span class="sxs-lookup"><span data-stu-id="3bcbc-141">Return value</span></span>

<span data-ttu-id="3bcbc-142">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3bcbc-143">定数</span><span class="sxs-lookup"><span data-stu-id="3bcbc-143">Constant</span></span>  |<span data-ttu-id="3bcbc-144">値</span><span class="sxs-lookup"><span data-stu-id="3bcbc-144">Value</span></span>  |<span data-ttu-id="3bcbc-145">説明</span><span class="sxs-lookup"><span data-stu-id="3bcbc-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="3bcbc-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="3bcbc-146">0x80041003</span></span> | <span data-ttu-id="3bcbc-147">ユーザーには、指定したクラスのインスタンスを表示するアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="3bcbc-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3bcbc-148">0x80041001</span></span> | <span data-ttu-id="3bcbc-149">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="3bcbc-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="3bcbc-150">0x80041010</span></span> | <span data-ttu-id="3bcbc-151">`strFilter` は存在しません。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3bcbc-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3bcbc-152">0x80041008</span></span> | <span data-ttu-id="3bcbc-153">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3bcbc-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3bcbc-154">0x80041006</span></span> | <span data-ttu-id="3bcbc-155">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="3bcbc-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="3bcbc-156">0x80041033</span></span> | <span data-ttu-id="3bcbc-157">WMI は、おそらく停止および再起動されました。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="3bcbc-158">呼び出す[ConnectServerWmi](connectserverwmi.md)もう一度です。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="3bcbc-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="3bcbc-159">0x80041015</span></span> | <span data-ttu-id="3bcbc-160">現在のプロセスと WMI のリモート プロシージャ コール (RPC) リンクに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3bcbc-161">0</span><span class="sxs-lookup"><span data-stu-id="3bcbc-161">0</span></span> | <span data-ttu-id="3bcbc-162">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-162">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="3bcbc-163">Remarks</span><span class="sxs-lookup"><span data-stu-id="3bcbc-163">Remarks</span></span>

<span data-ttu-id="3bcbc-164">この関数の呼び出しをラップする、 [iwbemservices::createclassenum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum)メソッド。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-164">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) method.</span></span>

<span data-ttu-id="3bcbc-165">返された列挙子が要素を持たないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="3bcbc-166">呼び出すことによって追加のエラー情報を取得するには、関数呼び出しに失敗した場合、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="3bcbc-167">必要条件</span><span class="sxs-lookup"><span data-stu-id="3bcbc-167">Requirements</span></span>

<span data-ttu-id="3bcbc-168">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bcbc-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="3bcbc-169">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3bcbc-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="3bcbc-170">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3bcbc-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3bcbc-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bcbc-171">See also</span></span>

- [<span data-ttu-id="3bcbc-172">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3bcbc-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
