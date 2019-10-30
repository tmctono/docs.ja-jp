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
ms.openlocfilehash: 9ffa718be0e8b67471fdf8cb277df201388d2840
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130404"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="7ec2f-103">CreateInstanceEnumWmi 関数</span><span class="sxs-lookup"><span data-stu-id="7ec2f-103">CreateInstanceEnumWmi function</span></span>

<span data-ttu-id="7ec2f-104">指定したクラスのインスタンスの中から指定した選択条件を満たすものを返す列挙子が返されます。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7ec2f-105">構文</span><span class="sxs-lookup"><span data-stu-id="7ec2f-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="7ec2f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7ec2f-106">Parameters</span></span>

`strFilter`\
<span data-ttu-id="7ec2f-107">からインスタンスが必要なクラスの名前。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="7ec2f-108">このパラメーターを `null` とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-108">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="7ec2f-109">からこの関数の動作に影響を与えるフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="7ec2f-110">次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7ec2f-111">定数</span><span class="sxs-lookup"><span data-stu-id="7ec2f-111">Constant</span></span>  |<span data-ttu-id="7ec2f-112">[値]</span><span class="sxs-lookup"><span data-stu-id="7ec2f-112">Value</span></span>  |<span data-ttu-id="7ec2f-113">説明</span><span class="sxs-lookup"><span data-stu-id="7ec2f-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="7ec2f-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="7ec2f-114">0x20000</span></span> | <span data-ttu-id="7ec2f-115">設定すると、関数は、現在の接続のロケールのローカライズされた名前空間に格納されている修正された修飾子を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="7ec2f-116">設定されていない場合、関数は、イミディエイト名前空間に格納されている修飾子だけを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="7ec2f-117">0</span><span class="sxs-lookup"><span data-stu-id="7ec2f-117">0</span></span> | <span data-ttu-id="7ec2f-118">列挙体には、階層内のこのおよびすべてのサブクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="7ec2f-119">1</span><span class="sxs-lookup"><span data-stu-id="7ec2f-119">1</span></span> | <span data-ttu-id="7ec2f-120">列挙体には、このクラスの純粋なインスタンスだけが含まれ、このクラスで見つからないプロパティを指定するサブクラスのすべてのインスタンスは除外されます。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="7ec2f-121">0x10</span><span class="sxs-lookup"><span data-stu-id="7ec2f-121">0x10</span></span> | <span data-ttu-id="7ec2f-122">このフラグにより、半同期呼び出しが発生します。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="7ec2f-123">0x20</span><span class="sxs-lookup"><span data-stu-id="7ec2f-123">0x20</span></span> | <span data-ttu-id="7ec2f-124">関数は、順方向専用の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="7ec2f-125">通常、順方向専用の列挙子は、従来の列挙子よりも高速で使用されるメモリが少なくなりますが、[複製](clone.md)の呼び出しは許可されません。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="7ec2f-126">0</span><span class="sxs-lookup"><span data-stu-id="7ec2f-126">0</span></span> | <span data-ttu-id="7ec2f-127">WMI は、列挙体が解放されるまで、そのオブジェクトへのポインターを保持します。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-127">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="7ec2f-128">最適なパフォーマンスを得るために、推奨されるフラグは `WBEM_FLAG_RETURN_IMMEDIATELY` と `WBEM_FLAG_FORWARD_ONLY` です。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="7ec2f-129">から通常、この値は `null`です。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="7ec2f-130">それ以外の場合は、要求されたインスタンスを提供しているプロバイダーによって使用される可能性のある[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)インスタンスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-130">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`\
<span data-ttu-id="7ec2f-131">入出力列挙子へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="7ec2f-132">から承認レベル。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-132">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="7ec2f-133">から偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-133">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="7ec2f-134">から現在の名前空間を表す[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-134">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="7ec2f-135">からユーザー名。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-135">[in] The user name.</span></span> <span data-ttu-id="7ec2f-136">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="7ec2f-137">からパスワード。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-137">[in] The password.</span></span> <span data-ttu-id="7ec2f-138">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="7ec2f-139">からユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-139">[in] The domain name of the user.</span></span> <span data-ttu-id="7ec2f-140">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="7ec2f-141">戻り値</span><span class="sxs-lookup"><span data-stu-id="7ec2f-141">Return value</span></span>

<span data-ttu-id="7ec2f-142">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7ec2f-143">定数</span><span class="sxs-lookup"><span data-stu-id="7ec2f-143">Constant</span></span>  |<span data-ttu-id="7ec2f-144">[値]</span><span class="sxs-lookup"><span data-stu-id="7ec2f-144">Value</span></span>  |<span data-ttu-id="7ec2f-145">説明</span><span class="sxs-lookup"><span data-stu-id="7ec2f-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="7ec2f-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="7ec2f-146">0x80041003</span></span> | <span data-ttu-id="7ec2f-147">指定されたクラスのインスタンスを表示する権限がユーザーにありません。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="7ec2f-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7ec2f-148">0x80041001</span></span> | <span data-ttu-id="7ec2f-149">特定できないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="7ec2f-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="7ec2f-150">0x80041010</span></span> | <span data-ttu-id="7ec2f-151">`strFilter` は存在しません。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7ec2f-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7ec2f-152">0x80041008</span></span> | <span data-ttu-id="7ec2f-153">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7ec2f-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7ec2f-154">0x80041006</span></span> | <span data-ttu-id="7ec2f-155">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="7ec2f-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="7ec2f-156">0x80041033</span></span> | <span data-ttu-id="7ec2f-157">WMI が停止し、再起動されたことがあります。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="7ec2f-158">[Connectserverwmi](connectserverwmi.md)を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="7ec2f-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="7ec2f-159">0x80041015</span></span> | <span data-ttu-id="7ec2f-160">現在のプロセスと WMI の間のリモートプロシージャコール (RPC) リンクが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7ec2f-161">0</span><span class="sxs-lookup"><span data-stu-id="7ec2f-161">0</span></span> | <span data-ttu-id="7ec2f-162">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-162">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="7ec2f-163">Remarks</span><span class="sxs-lookup"><span data-stu-id="7ec2f-163">Remarks</span></span>

<span data-ttu-id="7ec2f-164">この関数は、 [IWbemServices:: CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum)メソッドへの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-164">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) method.</span></span>

<span data-ttu-id="7ec2f-165">返される列挙子には、0個の要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="7ec2f-166">関数呼び出しが失敗した場合は、 [GetErrorInfo](geterrorinfo.md)関数を呼び出して追加のエラー情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ec2f-167">［要件］</span><span class="sxs-lookup"><span data-stu-id="7ec2f-167">Requirements</span></span>

<span data-ttu-id="7ec2f-168">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7ec2f-169">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="7ec2f-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="7ec2f-170">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7ec2f-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7ec2f-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ec2f-171">See also</span></span>

- [<span data-ttu-id="7ec2f-172">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7ec2f-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
