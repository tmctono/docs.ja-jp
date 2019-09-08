---
title: PutInstanceWmi 関数 (アンマネージ API リファレンス)
description: PutInstanceWmi 関数は、既存のクラスのインスタンスを作成または更新します。
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
ms.openlocfilehash: 37810ecab2e02d4ec250dd2a4b2657c3b898f714
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798374"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="36db4-103">PutInstanceWmi 関数</span><span class="sxs-lookup"><span data-stu-id="36db4-103">PutInstanceWmi function</span></span>

<span data-ttu-id="36db4-104">既存のクラスのインスタンスが作成または更新されます。</span><span class="sxs-lookup"><span data-stu-id="36db4-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="36db4-105">インスタンスは、WMI リポジトリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="36db4-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="36db4-106">構文</span><span class="sxs-lookup"><span data-stu-id="36db4-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="36db4-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="36db4-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="36db4-108">から書き込むインスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="36db4-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="36db4-109">からこの関数の動作に影響を与えるフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="36db4-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="36db4-110">次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="36db4-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="36db4-111">定数</span><span class="sxs-lookup"><span data-stu-id="36db4-111">Constant</span></span>  |<span data-ttu-id="36db4-112">Value</span><span class="sxs-lookup"><span data-stu-id="36db4-112">Value</span></span>  |<span data-ttu-id="36db4-113">説明</span><span class="sxs-lookup"><span data-stu-id="36db4-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="36db4-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="36db4-114">0x20000</span></span> | <span data-ttu-id="36db4-115">設定した場合、WMI は、**修正**されたフレーバーを持つ修飾子を格納しません。</span><span class="sxs-lookup"><span data-stu-id="36db4-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="36db4-116">設定されていない場合は、このオブジェクトがローカライズされていないと見なされ、すべての修飾子がこのインスタンスと共に格納されます。</span><span class="sxs-lookup"><span data-stu-id="36db4-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="36db4-117">0</span><span class="sxs-lookup"><span data-stu-id="36db4-117">0</span></span> | <span data-ttu-id="36db4-118">インスタンスが存在しない場合は作成し、既に存在する場合は上書きします。</span><span class="sxs-lookup"><span data-stu-id="36db4-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="36db4-119">1</span><span class="sxs-lookup"><span data-stu-id="36db4-119">1</span></span> | <span data-ttu-id="36db4-120">インスタンスを更新します。</span><span class="sxs-lookup"><span data-stu-id="36db4-120">Update the instance.</span></span> <span data-ttu-id="36db4-121">呼び出しを成功させるには、インスタンスが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="36db4-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="36db4-122">2</span><span class="sxs-lookup"><span data-stu-id="36db4-122">2</span></span> | <span data-ttu-id="36db4-123">インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="36db4-123">Create the instance.</span></span> <span data-ttu-id="36db4-124">インスタンスが既に存在する場合、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="36db4-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="36db4-125">0x10</span><span class="sxs-lookup"><span data-stu-id="36db4-125">0x10</span></span> | <span data-ttu-id="36db4-126">このフラグにより、半同期呼び出しが発生します。</span><span class="sxs-lookup"><span data-stu-id="36db4-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="36db4-127">から通常、この値は`null`です。</span><span class="sxs-lookup"><span data-stu-id="36db4-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="36db4-128">それ以外の場合は、要求されたクラスを提供しているプロバイダーが使用できる[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)インスタンスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="36db4-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="36db4-129">入出力の`null`場合、このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="36db4-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="36db4-130">に`lFlags`が`WBEM_FLAG_RETURN_IMMEDIATELY`含まれている場合、 `WBEM_S_NO_ERROR`関数はを使用してすぐにを返します。</span><span class="sxs-lookup"><span data-stu-id="36db4-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="36db4-131">パラメーター `ppCallResult`は、新しい[IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult)オブジェクトへのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="36db4-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="36db4-132">戻り値</span><span class="sxs-lookup"><span data-stu-id="36db4-132">Return value</span></span>

<span data-ttu-id="36db4-133">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="36db4-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="36db4-134">定数</span><span class="sxs-lookup"><span data-stu-id="36db4-134">Constant</span></span>  |<span data-ttu-id="36db4-135">Value</span><span class="sxs-lookup"><span data-stu-id="36db4-135">Value</span></span>  |<span data-ttu-id="36db4-136">説明</span><span class="sxs-lookup"><span data-stu-id="36db4-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="36db4-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="36db4-137">0x80041003</span></span> | <span data-ttu-id="36db4-138">指定されたクラスのインスタンスを更新するためのアクセス許可がユーザーにありません。</span><span class="sxs-lookup"><span data-stu-id="36db4-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="36db4-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="36db4-139">0x80041001</span></span> | <span data-ttu-id="36db4-140">特定できないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="36db4-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="36db4-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="36db4-141">0x80041010</span></span> | <span data-ttu-id="36db4-142">このインスタンスをサポートしているクラスが無効です。</span><span class="sxs-lookup"><span data-stu-id="36db4-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="36db4-143">0x80048</span><span class="sxs-lookup"><span data-stu-id="36db4-143">0x80041028</span></span> | <span data-ttu-id="36db4-144">は、**インデックス付き**または**Not_Null**修飾子に`null`よってマークされたプロパティなど、ではできないプロパティに対して指定されました。`null`</span><span class="sxs-lookup"><span data-stu-id="36db4-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="36db4-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="36db4-145">0x8004100f</span></span> | <span data-ttu-id="36db4-146">指定されたインスタンスは無効です。</span><span class="sxs-lookup"><span data-stu-id="36db4-146">The specified instance is not valid.</span></span> <span data-ttu-id="36db4-147">(たとえば、クラスを`PutInstanceWmi`使用してを呼び出すと、この値が返されます)。</span><span class="sxs-lookup"><span data-stu-id="36db4-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="36db4-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="36db4-148">0x80041008</span></span> | <span data-ttu-id="36db4-149">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="36db4-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="36db4-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="36db4-150">0x80041019</span></span> | <span data-ttu-id="36db4-151">`WBEM_FLAG_CREATE_ONLY`フラグが指定されましたが、インスタンスは既に存在します。</span><span class="sxs-lookup"><span data-stu-id="36db4-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="36db4-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="36db4-152">0x80041002</span></span> | <span data-ttu-id="36db4-153">`WBEM_FLAG_UPDATE_ONLY`はで`lFlags`指定されましたが、インスタンスが存在しません。</span><span class="sxs-lookup"><span data-stu-id="36db4-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="36db4-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="36db4-154">0x80041006</span></span> | <span data-ttu-id="36db4-155">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="36db4-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="36db4-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="36db4-156">0x80041033</span></span> | <span data-ttu-id="36db4-157">WMI が停止し、再起動されたことがあります。</span><span class="sxs-lookup"><span data-stu-id="36db4-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="36db4-158">[Connectserverwmi](connectserverwmi.md)を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="36db4-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="36db4-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="36db4-159">0x80041015</span></span> | <span data-ttu-id="36db4-160">現在のプロセスと WMI の間のリモートプロシージャコール (RPC) リンクが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="36db4-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="36db4-161">0</span><span class="sxs-lookup"><span data-stu-id="36db4-161">0</span></span> | <span data-ttu-id="36db4-162">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="36db4-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="36db4-163">Remarks</span><span class="sxs-lookup"><span data-stu-id="36db4-163">Remarks</span></span>

<span data-ttu-id="36db4-164">この関数は、 [IWbemServices::P utInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="36db4-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="36db4-165">関数`PutInstanceWmi`では、インスタンスの作成と、既存のクラスのインスタンスの更新のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="36db4-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="36db4-166">`pCtx`パラメーターの設定方法によっては、インスタンスの一部またはすべてのプロパティが更新されます。</span><span class="sxs-lookup"><span data-stu-id="36db4-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="36db4-167">によってポイントされる`pInst`インスタンスがサブクラスに属している場合、Windows Management は、サブクラスの派生元であるクラスを担当するすべてのプロバイダーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="36db4-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="36db4-168">元`PutInstanceWmi`の要求を成功させるには、これらのプロバイダーのすべてが成功する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36db4-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="36db4-169">階層内の最上位のクラスをサポートするプロバイダーが最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="36db4-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="36db4-170">呼び出し順序は最上位クラスのサブクラスから続行され、Windows Management がによって`pInst`ポイントされたインスタンスを所有するクラスのプロバイダーに到達するまで、上から下に進みます。</span><span class="sxs-lookup"><span data-stu-id="36db4-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="36db4-171">Windows Management では、インスタンスのどの子クラスに対してもプロバイダーは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="36db4-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="36db4-172">クラス階層に属しているインスタンスをアプリケーションで更新する必要がある`pInst`場合、パラメーターは、変更するプロパティを含むインスタンスを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="36db4-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="36db4-173">つまり、 **Classb**に属するターゲットインスタンスを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="36db4-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="36db4-174">**Classb**インスタンスは**classb**から派生し、 **Classb**はプロパティ**propa**を定義します。</span><span class="sxs-lookup"><span data-stu-id="36db4-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="36db4-175">アプリケーションで**classb**インスタンスの**propa**の値を変更する場合は、 **classb**のインスタンスではなく`pInst` 、そのインスタンスに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36db4-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="36db4-176">抽象`PutInstanceWmi`クラスのインスタンスでを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="36db4-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="36db4-177">関数呼び出しが失敗した場合は、 [GetErrorInfo](geterrorinfo.md)関数を呼び出して追加のエラー情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="36db4-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="36db4-178">必要条件</span><span class="sxs-lookup"><span data-stu-id="36db4-178">Requirements</span></span>

<span data-ttu-id="36db4-179">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db4-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="36db4-180">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="36db4-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="36db4-181">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="36db4-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="36db4-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="36db4-182">See also</span></span>

- [<span data-ttu-id="36db4-183">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="36db4-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
