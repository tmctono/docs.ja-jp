---
title: PutInstanceWmi 関数 (アンマネージ API リファレンス)
description: PutInstanceWmi 関数を作成または既存のクラスのインスタンスを更新します。
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9774656d010a3e52dd2392094ba6b529a573f3e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636567"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="b90d2-103">PutInstanceWmi 関数</span><span class="sxs-lookup"><span data-stu-id="b90d2-103">PutInstanceWmi function</span></span>

<span data-ttu-id="b90d2-104">既存のクラスのインスタンスが作成または更新されます。</span><span class="sxs-lookup"><span data-stu-id="b90d2-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="b90d2-105">インスタンスは、WMI リポジトリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b90d2-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b90d2-106">構文</span><span class="sxs-lookup"><span data-stu-id="b90d2-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="b90d2-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b90d2-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="b90d2-108">[in]書き込まれるインスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b90d2-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="b90d2-109">[in]この関数の動作に影響するフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="b90d2-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="b90d2-110">次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b90d2-111">定数</span><span class="sxs-lookup"><span data-stu-id="b90d2-111">Constant</span></span>  |<span data-ttu-id="b90d2-112">値</span><span class="sxs-lookup"><span data-stu-id="b90d2-112">Value</span></span>  |<span data-ttu-id="b90d2-113">説明</span><span class="sxs-lookup"><span data-stu-id="b90d2-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="b90d2-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="b90d2-114">0x20000</span></span> | <span data-ttu-id="b90d2-115">かどうか設定、WMI は保存されませんで任意の修飾子、 **Amended**フレーバー。</span><span class="sxs-lookup"><span data-stu-id="b90d2-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="b90d2-116">指定しない場合、このオブジェクトがローカライズされていないことと、すべての修飾子がこのインスタンスに格納されていること前提は、セット。</span><span class="sxs-lookup"><span data-stu-id="b90d2-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="b90d2-117">0</span><span class="sxs-lookup"><span data-stu-id="b90d2-117">0</span></span> | <span data-ttu-id="b90d2-118">存在したり、既に存在する場合は、上書きしない場合は、インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="b90d2-119">1</span><span class="sxs-lookup"><span data-stu-id="b90d2-119">1</span></span> | <span data-ttu-id="b90d2-120">インスタンスを更新します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-120">Update the instance.</span></span> <span data-ttu-id="b90d2-121">呼び出しが成功するは、インスタンスが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b90d2-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="b90d2-122">2</span><span class="sxs-lookup"><span data-stu-id="b90d2-122">2</span></span> | <span data-ttu-id="b90d2-123">インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-123">Create the instance.</span></span> <span data-ttu-id="b90d2-124">インスタンスが既に存在する場合、呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="b90d2-125">0x10</span><span class="sxs-lookup"><span data-stu-id="b90d2-125">0x10</span></span> | <span data-ttu-id="b90d2-126">フラグには、半同期的メソッドの呼び出しが行わします。</span><span class="sxs-lookup"><span data-stu-id="b90d2-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="b90d2-127">[in]この値は、通常、`null`します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="b90d2-128">ポインターは、それ以外の場合、 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)インスタンスを要求されたクラスを提供しているプロバイダーによって使用されることができます。</span><span class="sxs-lookup"><span data-stu-id="b90d2-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="b90d2-129">[out]場合`null`、このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="b90d2-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="b90d2-130">場合`lFlags`を含む`WBEM_FLAG_RETURN_IMMEDIATELY`、関数を直ちに返します`WBEM_S_NO_ERROR`します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="b90d2-131">`ppCallResult`パラメーターは、新しいへのポインターを受け取ります[IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b90d2-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="b90d2-132">戻り値</span><span class="sxs-lookup"><span data-stu-id="b90d2-132">Return value</span></span>

<span data-ttu-id="b90d2-133">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b90d2-134">定数</span><span class="sxs-lookup"><span data-stu-id="b90d2-134">Constant</span></span>  |<span data-ttu-id="b90d2-135">値</span><span class="sxs-lookup"><span data-stu-id="b90d2-135">Value</span></span>  |<span data-ttu-id="b90d2-136">説明</span><span class="sxs-lookup"><span data-stu-id="b90d2-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="b90d2-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="b90d2-137">0x80041003</span></span> | <span data-ttu-id="b90d2-138">ユーザーには、指定したクラスのインスタンスを更新するアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="b90d2-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="b90d2-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b90d2-139">0x80041001</span></span> | <span data-ttu-id="b90d2-140">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b90d2-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="b90d2-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="b90d2-141">0x80041010</span></span> | <span data-ttu-id="b90d2-142">このインスタンスをサポートしているクラスが無効です。</span><span class="sxs-lookup"><span data-stu-id="b90d2-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="b90d2-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="b90d2-143">0x80041028</span></span> | <span data-ttu-id="b90d2-144">`null`できないプロパティが指定されました`null`、いずれかでマークされているなど、**インデックス**または**not_** 修飾子。</span><span class="sxs-lookup"><span data-stu-id="b90d2-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="b90d2-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="b90d2-145">0x8004100f</span></span> | <span data-ttu-id="b90d2-146">指定したインスタンスが無効です。</span><span class="sxs-lookup"><span data-stu-id="b90d2-146">The specified instance is not valid.</span></span> <span data-ttu-id="b90d2-147">(たとえば、呼び出し`PutInstanceWmi`クラスには、この値を返します)。</span><span class="sxs-lookup"><span data-stu-id="b90d2-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b90d2-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b90d2-148">0x80041008</span></span> | <span data-ttu-id="b90d2-149">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="b90d2-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="b90d2-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="b90d2-150">0x80041019</span></span> | <span data-ttu-id="b90d2-151">`WBEM_FLAG_CREATE_ONLY`フラグが指定されましたが、インスタンスが既に存在します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="b90d2-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b90d2-152">0x80041002</span></span> | <span data-ttu-id="b90d2-153">`WBEM_FLAG_UPDATE_ONLY` 指定された`lFlags`が、インスタンスが存在しません。</span><span class="sxs-lookup"><span data-stu-id="b90d2-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b90d2-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b90d2-154">0x80041006</span></span> | <span data-ttu-id="b90d2-155">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="b90d2-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="b90d2-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="b90d2-156">0x80041033</span></span> | <span data-ttu-id="b90d2-157">WMI は、おそらく停止および再起動されました。</span><span class="sxs-lookup"><span data-stu-id="b90d2-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="b90d2-158">呼び出す[ConnectServerWmi](connectserverwmi.md)もう一度です。</span><span class="sxs-lookup"><span data-stu-id="b90d2-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="b90d2-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="b90d2-159">0x80041015</span></span> | <span data-ttu-id="b90d2-160">現在のプロセスと WMI のリモート プロシージャ コール (RPC) リンクに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="b90d2-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b90d2-161">0</span><span class="sxs-lookup"><span data-stu-id="b90d2-161">0</span></span> | <span data-ttu-id="b90d2-162">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="b90d2-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b90d2-163">Remarks</span><span class="sxs-lookup"><span data-stu-id="b90d2-163">Remarks</span></span>

<span data-ttu-id="b90d2-164">この関数の呼び出しをラップする、 [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance)メソッド。</span><span class="sxs-lookup"><span data-stu-id="b90d2-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="b90d2-165">`PutInstanceWmi`関数のインスタンスを作成して、既存クラスのインスタンスの更新をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b90d2-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="b90d2-166">方法に応じて`pCtx`パラメーターが設定されていると、一部またはすべてのインスタンスのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="b90d2-167">ときに、インスタンスによって示される`pInst`サブクラスが派生するクラスを担当するすべてのプロバイダーの呼び出し、サブクラスでは、Windows の管理に属しています。</span><span class="sxs-lookup"><span data-stu-id="b90d2-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="b90d2-168">元のこれらのプロバイダーのすべてが成功する必要があります`PutInstanceWmi`の要求に成功します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="b90d2-169">階層の最上位のクラスをサポートしているプロバイダーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b90d2-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="b90d2-170">呼び出しの順序が最上位のクラスのサブクラスを続行し、Windows 管理によって示されるインスタンスを所有しているクラスのプロバイダーに到達するまで、上から下に進みます`pInst`します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="b90d2-171">Windows の管理には、インスタンスの子クラスのいずれかのプロバイダーは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="b90d2-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="b90d2-172">アプリケーションが、クラス階層に属しているインスタンスを更新する必要がありますと、`pInst`パラメーターは、変更するプロパティを含むインスタンスを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b90d2-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="b90d2-173">つまり、ターゲット インスタンスが属しているを検討**ClassB**します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="b90d2-174">**ClassB**から派生したインスタンス**ClassA**、および**ClassA**プロパティを定義**PropA**します。</span><span class="sxs-lookup"><span data-stu-id="b90d2-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="b90d2-175">アプリケーションがの値を変更するか**PropA**で、 **ClassB**設定する必要がありますのインスタンス、`pInst`のインスタンスではなく、そのインスタンスに**ClassA**.</span><span class="sxs-lookup"><span data-stu-id="b90d2-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="b90d2-176">呼び出す`PutInstanceWmi`抽象クラスのインスタンスでは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="b90d2-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="b90d2-177">呼び出すことによって追加のエラー情報を取得するには、関数呼び出しに失敗した場合、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="b90d2-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="b90d2-178">必要条件</span><span class="sxs-lookup"><span data-stu-id="b90d2-178">Requirements</span></span>

<span data-ttu-id="b90d2-179">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b90d2-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b90d2-180">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b90d2-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="b90d2-181">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b90d2-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b90d2-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="b90d2-182">See also</span></span>

- [<span data-ttu-id="b90d2-183">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b90d2-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
