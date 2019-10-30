---
title: PutClassWmi 関数 (アンマネージ API リファレンス)
description: PutClassWmi 関数は、新しいクラスを作成するか、既存のクラスを更新します。
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 95a5e1f6339bde9dfe5c5ad9f989fc06e10fa7f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101788"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="e3dd8-103">PutClassWmi 関数</span><span class="sxs-lookup"><span data-stu-id="e3dd8-103">PutClassWmi function</span></span>

<span data-ttu-id="e3dd8-104">新しいクラスが作成されるか、既存のクラスが更新されます。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-104">Creates a new class or updates an existing one.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e3dd8-105">構文</span><span class="sxs-lookup"><span data-stu-id="e3dd8-105">Syntax</span></span>

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="e3dd8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3dd8-106">Parameters</span></span>

`pObject`\
<span data-ttu-id="e3dd8-107">から有効なクラス定義へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="e3dd8-108">この値は、必要なすべてのプロパティ値で正しく初期化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`\
<span data-ttu-id="e3dd8-109">からこの関数の動作に影響を与えるフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="e3dd8-110">次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e3dd8-111">定数</span><span class="sxs-lookup"><span data-stu-id="e3dd8-111">Constant</span></span>  |<span data-ttu-id="e3dd8-112">[値]</span><span class="sxs-lookup"><span data-stu-id="e3dd8-112">Value</span></span>  |<span data-ttu-id="e3dd8-113">説明</span><span class="sxs-lookup"><span data-stu-id="e3dd8-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="e3dd8-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="e3dd8-114">0x20000</span></span> | <span data-ttu-id="e3dd8-115">設定した場合、WMI は、修正されたフレーバーを持つ修飾子を格納しません。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> <br> <span data-ttu-id="e3dd8-116">設定されていない場合は、このオブジェクトがローカライズされていないと見なされ、すべての修飾子がこのインスタンスと共に格納されます。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="e3dd8-117">0</span><span class="sxs-lookup"><span data-stu-id="e3dd8-117">0</span></span> | <span data-ttu-id="e3dd8-118">クラスが存在しない場合は作成し、既に存在する場合は上書きします。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="e3dd8-119">1</span><span class="sxs-lookup"><span data-stu-id="e3dd8-119">1</span></span> | <span data-ttu-id="e3dd8-120">クラスを更新します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-120">Update the class.</span></span> <span data-ttu-id="e3dd8-121">呼び出しを成功させるには、クラスが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="e3dd8-122">2</span><span class="sxs-lookup"><span data-stu-id="e3dd8-122">2</span></span> | <span data-ttu-id="e3dd8-123">クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-123">Create the class.</span></span> <span data-ttu-id="e3dd8-124">クラスが既に存在する場合、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="e3dd8-125">0x10</span><span class="sxs-lookup"><span data-stu-id="e3dd8-125">0x10</span></span> | <span data-ttu-id="e3dd8-126">このフラグにより、半同期呼び出しが発生します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="e3dd8-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="e3dd8-127">0x10000</span></span> | <span data-ttu-id="e3dd8-128">プッシュプロバイダーは、このクラスが変更されたことを示すために `PutClassWmi` を呼び出すときにこのフラグを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="e3dd8-129">0</span><span class="sxs-lookup"><span data-stu-id="e3dd8-129">0</span></span> | <span data-ttu-id="e3dd8-130">派生クラスとそのクラスのインスタンスが存在しない場合に、クラスを更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="e3dd8-131">また、説明の修飾子などの重要でない修飾子だけが変更された場合にも、すべての更新が可能になります。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="e3dd8-132">クラスにインスタンスがある場合、または重要な修飾子が変更された場合、更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="e3dd8-133">0x20</span><span class="sxs-lookup"><span data-stu-id="e3dd8-133">0x20</span></span> | <span data-ttu-id="e3dd8-134">変更によって子クラスとの競合が発生しない限り、子クラスがある場合でも、クラスを更新できます。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="e3dd8-135">たとえば、このフラグを使用すると、前に子クラスには記載されていなかった基本クラスに新しいプロパティを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="e3dd8-136">クラスにインスタンスがある場合、更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="e3dd8-137">0x40</span><span class="sxs-lookup"><span data-stu-id="e3dd8-137">0x40</span></span> | <span data-ttu-id="e3dd8-138">競合する子クラスが存在する場合に、クラスを強制的に更新します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="e3dd8-139">たとえば、このフラグは、子クラスでクラス修飾子が定義されている場合に更新を強制します。基底クラスは、既存の修飾子と競合する同じ修飾子を追加しようとします。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with the existing one.</span></span> <span data-ttu-id="e3dd8-140">Force モードでは、子クラスの競合している修飾子を削除することによって、このような競合が解決されます。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`\
<span data-ttu-id="e3dd8-141">から通常、この値は `null`です。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="e3dd8-142">それ以外の場合は、要求されたクラスを提供しているプロバイダーが使用できる[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)インスタンスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="e3dd8-143">入出力`null`した場合、このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="e3dd8-144">`lFlags` に `WBEM_FLAG_RETURN_IMMEDIATELY`が含まれている場合、関数はすぐに `WBEM_S_NO_ERROR`を返します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="e3dd8-145">`ppCallResult` パラメーターは、新しい[IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult)オブジェクトへのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="e3dd8-146">戻り値</span><span class="sxs-lookup"><span data-stu-id="e3dd8-146">Return value</span></span>

<span data-ttu-id="e3dd8-147">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e3dd8-148">定数</span><span class="sxs-lookup"><span data-stu-id="e3dd8-148">Constant</span></span>  |<span data-ttu-id="e3dd8-149">[値]</span><span class="sxs-lookup"><span data-stu-id="e3dd8-149">Value</span></span>  |<span data-ttu-id="e3dd8-150">説明</span><span class="sxs-lookup"><span data-stu-id="e3dd8-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="e3dd8-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="e3dd8-151">0x80041003</span></span> | <span data-ttu-id="e3dd8-152">ユーザーには、クラスを作成または変更するためのアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="e3dd8-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e3dd8-153">0x80041001</span></span> | <span data-ttu-id="e3dd8-154">特定できないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="e3dd8-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="e3dd8-155">0x80041010</span></span> | <span data-ttu-id="e3dd8-156">指定されたクラスは無効です。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-156">The specified class is not valid.</span></span> <span data-ttu-id="e3dd8-157">通常、これは `pObject` がインスタンスオブジェクトを指定していることを示します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e3dd8-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e3dd8-158">0x80041008</span></span> | <span data-ttu-id="e3dd8-159">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="e3dd8-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="e3dd8-160">0x80041016</span></span> | <span data-ttu-id="e3dd8-161">指定されたクラス名が無効です。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="e3dd8-162">0x8004-5</span><span class="sxs-lookup"><span data-stu-id="e3dd8-162">0x80041025</span></span> | <span data-ttu-id="e3dd8-163">サブクラスを無効にする変更を加えようとしました。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="e3dd8-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="e3dd8-164">0x80041019</span></span> | <span data-ttu-id="e3dd8-165">`WBEM_FLAG_CREATE_ONLY` フラグが指定されましたが、このクラスは既に存在します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="e3dd8-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e3dd8-166">0x80041002</span></span> | <span data-ttu-id="e3dd8-167">`lFlags`に `WBEM_FLAG_UPDATE_ONLY` が指定されましたが、クラスが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="e3dd8-168">0x80040</span><span class="sxs-lookup"><span data-stu-id="e3dd8-168">0x80041020</span></span> | <span data-ttu-id="e3dd8-169">クラスの必須プロパティがすべて設定されていません。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e3dd8-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e3dd8-170">0x80041006</span></span> | <span data-ttu-id="e3dd8-171">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="e3dd8-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="e3dd8-172">0x80041033</span></span> | <span data-ttu-id="e3dd8-173">WMI が停止し、再起動されたことがあります。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="e3dd8-174">[Connectserverwmi](connectserverwmi.md)を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="e3dd8-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="e3dd8-175">0x80041015</span></span> | <span data-ttu-id="e3dd8-176">現在のプロセスと WMI の間のリモートプロシージャコール (RPC) リンクが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e3dd8-177">0</span><span class="sxs-lookup"><span data-stu-id="e3dd8-177">0</span></span> | <span data-ttu-id="e3dd8-178">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-178">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e3dd8-179">Remarks</span><span class="sxs-lookup"><span data-stu-id="e3dd8-179">Remarks</span></span>

<span data-ttu-id="e3dd8-180">この関数は、 [IWbemServices::P utClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="e3dd8-181">ユーザーは、名前の先頭または末尾にアンダースコア文字を持つクラスを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-181">The user may not create classes with names that begin or end with an underscore character.</span></span>

<span data-ttu-id="e3dd8-182">関数呼び出しが失敗した場合は、 [GetErrorInfo](geterrorinfo.md)関数を呼び出して追加のエラー情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="e3dd8-183">［要件］</span><span class="sxs-lookup"><span data-stu-id="e3dd8-183">Requirements</span></span>

<span data-ttu-id="e3dd8-184">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3dd8-184">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e3dd8-185">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="e3dd8-185">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e3dd8-186">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e3dd8-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e3dd8-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3dd8-187">See also</span></span>

- [<span data-ttu-id="e3dd8-188">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e3dd8-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
