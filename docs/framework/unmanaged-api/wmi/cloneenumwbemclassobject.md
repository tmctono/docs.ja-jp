---
title: CloneEnumWbemClassObject 関数 (アンマネージ API リファレンス)
description: CloneEnumWbemClassObject 関数では、列挙子の論理コピーを作成します。
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7b384bb24cbf7ab7379949fd85a22121a1310e3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636866"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="6b913-103">CloneEnumWbemClassObject 関数</span><span class="sxs-lookup"><span data-stu-id="6b913-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="6b913-104">列挙型内での位置を維持して、列挙子の論理コピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b913-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6b913-105">構文</span><span class="sxs-lookup"><span data-stu-id="6b913-105">Syntax</span></span>

```
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```

## <a name="parameters"></a><span data-ttu-id="6b913-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b913-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="6b913-107">[out]新しいへのポインターを受け取る[IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)します。</span><span class="sxs-lookup"><span data-stu-id="6b913-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="6b913-108">[in]承認レベル。</span><span class="sxs-lookup"><span data-stu-id="6b913-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="6b913-109">[in]偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="6b913-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="6b913-110">[out]ポインター、 [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)クローンを作成するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="6b913-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="6b913-111">[in]ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="6b913-111">[in] The user name.</span></span> <span data-ttu-id="6b913-112">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="6b913-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="6b913-113">[in]パスワードです。</span><span class="sxs-lookup"><span data-stu-id="6b913-113">[in] The password.</span></span> <span data-ttu-id="6b913-114">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="6b913-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="6b913-115">`strAuthority`\ [in] ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="6b913-115">`strAuthority`\ [in] The domain name of the user.</span></span> <span data-ttu-id="6b913-116">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="6b913-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="6b913-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="6b913-117">Return value</span></span>

<span data-ttu-id="6b913-118">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="6b913-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6b913-119">定数</span><span class="sxs-lookup"><span data-stu-id="6b913-119">Constant</span></span>  |<span data-ttu-id="6b913-120">値</span><span class="sxs-lookup"><span data-stu-id="6b913-120">Value</span></span>  |<span data-ttu-id="6b913-121">説明</span><span class="sxs-lookup"><span data-stu-id="6b913-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="6b913-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6b913-122">0x80041001</span></span> | <span data-ttu-id="6b913-123">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6b913-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6b913-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6b913-124">0x80041008</span></span> | <span data-ttu-id="6b913-125">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="6b913-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6b913-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6b913-126">0x80041006</span></span> | <span data-ttu-id="6b913-127">十分なメモリが使用可能な操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="6b913-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="6b913-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="6b913-128">0x80041015</span></span> | <span data-ttu-id="6b913-129">現在のプロセスと WMI のリモート プロシージャ コール (RPC) リンクに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6b913-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6b913-130">0</span><span class="sxs-lookup"><span data-stu-id="6b913-130">0</span></span> | <span data-ttu-id="6b913-131">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="6b913-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="6b913-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="6b913-132">Remarks</span></span>

<span data-ttu-id="6b913-133">この関数の呼び出しをラップする、 [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)メソッド。</span><span class="sxs-lookup"><span data-stu-id="6b913-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="6b913-134">このメソッドは、「ベスト エフォート」コピーのみです。</span><span class="sxs-lookup"><span data-stu-id="6b913-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="6b913-135">多くの CIM オブジェクトの動的な性質のためことは新しい列挙子がソースの列挙子と同じオブジェクトのセットを列挙できません。</span><span class="sxs-lookup"><span data-stu-id="6b913-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="6b913-136">呼び出すことによって追加のエラー情報を取得するには、関数呼び出しに失敗した場合、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="6b913-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="6b913-137">例</span><span class="sxs-lookup"><span data-stu-id="6b913-137">Example</span></span>

<span data-ttu-id="6b913-138">例については、次を参照してください。、 [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)メソッド。</span><span class="sxs-lookup"><span data-stu-id="6b913-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6b913-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b913-139">Requirements</span></span>
 <span data-ttu-id="6b913-140">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b913-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="6b913-141">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6b913-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="6b913-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6b913-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6b913-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b913-143">See also</span></span>

- [<span data-ttu-id="6b913-144">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6b913-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
