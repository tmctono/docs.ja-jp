---
title: 関数 (アンマネージ API リファレンス)
description: 関数は列挙子の論理コピーを作成します。
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
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175019"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="87927-103">CloneEnumWbemClassObject 関数</span><span class="sxs-lookup"><span data-stu-id="87927-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="87927-104">列挙型内での位置を維持して、列挙子の論理コピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87927-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="87927-105">構文</span><span class="sxs-lookup"><span data-stu-id="87927-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="87927-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87927-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="87927-107">[アウト]新しい[IEnumWbemClass オブジェクト](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="87927-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="87927-108">[in]権限レベル。</span><span class="sxs-lookup"><span data-stu-id="87927-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="87927-109">[in]偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="87927-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="87927-110">[アウト]複製される[インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="87927-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="87927-111">[in]ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="87927-111">[in] The user name.</span></span> <span data-ttu-id="87927-112">詳細については、[関数](connectserverwmi.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87927-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="87927-113">[in]パスワード。</span><span class="sxs-lookup"><span data-stu-id="87927-113">[in] The password.</span></span> <span data-ttu-id="87927-114">詳細については、[関数](connectserverwmi.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87927-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="87927-115">[in]ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="87927-115">[in] The domain name of the user.</span></span> <span data-ttu-id="87927-116">詳細については、[関数](connectserverwmi.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87927-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="87927-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="87927-117">Return value</span></span>

<span data-ttu-id="87927-118">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="87927-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="87927-119">常時</span><span class="sxs-lookup"><span data-stu-id="87927-119">Constant</span></span>  |<span data-ttu-id="87927-120">Value</span><span class="sxs-lookup"><span data-stu-id="87927-120">Value</span></span>  |<span data-ttu-id="87927-121">説明</span><span class="sxs-lookup"><span data-stu-id="87927-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="87927-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="87927-122">0x80041001</span></span> | <span data-ttu-id="87927-123">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="87927-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="87927-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="87927-124">0x80041008</span></span> | <span data-ttu-id="87927-125">パラメータが無効です。</span><span class="sxs-lookup"><span data-stu-id="87927-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="87927-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="87927-126">0x80041006</span></span> | <span data-ttu-id="87927-127">メモリ不足が発生し、操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="87927-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="87927-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="87927-128">0x80041015</span></span> | <span data-ttu-id="87927-129">現在のプロセスと WMI 間のリモート プロシージャ コール (RPC) リンクに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="87927-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="87927-130">0</span><span class="sxs-lookup"><span data-stu-id="87927-130">0</span></span> | <span data-ttu-id="87927-131">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="87927-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="87927-132">解説</span><span class="sxs-lookup"><span data-stu-id="87927-132">Remarks</span></span>

<span data-ttu-id="87927-133">この関数は、メソッドの呼び出しをラップ[します](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)。</span><span class="sxs-lookup"><span data-stu-id="87927-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="87927-134">この方法では、"ベスト エフォート" コピーのみが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87927-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="87927-135">多くの CIM オブジェクトの動的な性質により、新しい列挙子がソース列挙子と同じオブジェクトのセットを列挙しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="87927-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="87927-136">関数呼び出しが失敗した場合は[、GetErrorInfo](geterrorinfo.md)関数を呼び出すことによって、追加のエラー情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="87927-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="87927-137">例</span><span class="sxs-lookup"><span data-stu-id="87927-137">Example</span></span>

<span data-ttu-id="87927-138">例については、[メソッド](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87927-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="87927-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="87927-139">Requirements</span></span>
 <span data-ttu-id="87927-140">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87927-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="87927-141">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="87927-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="87927-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="87927-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="87927-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="87927-143">See also</span></span>

- [<span data-ttu-id="87927-144">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="87927-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
