---
title: CloneEnumWbemClassObject 関数 (アンマネージ API リファレンス)
description: CloneEnumWbemClassObject 関数は、列挙子の論理コピーを作成します。
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
ms.openlocfilehash: 1605314f94fd82d2a2cd7be105dde9e273f607bc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798699"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="ea88f-103">CloneEnumWbemClassObject 関数</span><span class="sxs-lookup"><span data-stu-id="ea88f-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="ea88f-104">列挙型内での位置を維持して、列挙子の論理コピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea88f-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ea88f-105">構文</span><span class="sxs-lookup"><span data-stu-id="ea88f-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="ea88f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea88f-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="ea88f-107">入出力新しい[IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea88f-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="ea88f-108">から承認レベル。</span><span class="sxs-lookup"><span data-stu-id="ea88f-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="ea88f-109">から偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="ea88f-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="ea88f-110">入出力複製する[IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ea88f-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="ea88f-111">からユーザー名。</span><span class="sxs-lookup"><span data-stu-id="ea88f-111">[in] The user name.</span></span> <span data-ttu-id="ea88f-112">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea88f-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="ea88f-113">からパスワード。</span><span class="sxs-lookup"><span data-stu-id="ea88f-113">[in] The password.</span></span> <span data-ttu-id="ea88f-114">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea88f-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="ea88f-115">`strAuthority`\ [入力] ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="ea88f-115">`strAuthority`\ [in] The domain name of the user.</span></span> <span data-ttu-id="ea88f-116">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea88f-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="ea88f-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="ea88f-117">Return value</span></span>

<span data-ttu-id="ea88f-118">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea88f-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ea88f-119">定数</span><span class="sxs-lookup"><span data-stu-id="ea88f-119">Constant</span></span>  |<span data-ttu-id="ea88f-120">Value</span><span class="sxs-lookup"><span data-stu-id="ea88f-120">Value</span></span>  |<span data-ttu-id="ea88f-121">説明</span><span class="sxs-lookup"><span data-stu-id="ea88f-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="ea88f-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ea88f-122">0x80041001</span></span> | <span data-ttu-id="ea88f-123">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ea88f-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ea88f-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ea88f-124">0x80041008</span></span> | <span data-ttu-id="ea88f-125">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="ea88f-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ea88f-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ea88f-126">0x80041006</span></span> | <span data-ttu-id="ea88f-127">使用可能なメモリが不足しているため、操作を完了できません。</span><span class="sxs-lookup"><span data-stu-id="ea88f-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="ea88f-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="ea88f-128">0x80041015</span></span> | <span data-ttu-id="ea88f-129">現在のプロセスと WMI の間のリモートプロシージャコール (RPC) リンクが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="ea88f-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ea88f-130">0</span><span class="sxs-lookup"><span data-stu-id="ea88f-130">0</span></span> | <span data-ttu-id="ea88f-131">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="ea88f-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ea88f-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="ea88f-132">Remarks</span></span>

<span data-ttu-id="ea88f-133">この関数は、 [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="ea88f-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="ea88f-134">このメソッドは、"ベストエフォート" コピーだけを行います。</span><span class="sxs-lookup"><span data-stu-id="ea88f-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="ea88f-135">多くの CIM オブジェクトは動的な性質を持つため、新しい列挙子がソース列挙子と同じオブジェクトのセットを列挙しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea88f-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="ea88f-136">関数呼び出しが失敗した場合は、 [GetErrorInfo](geterrorinfo.md)関数を呼び出して追加のエラー情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ea88f-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="ea88f-137">例</span><span class="sxs-lookup"><span data-stu-id="ea88f-137">Example</span></span>

<span data-ttu-id="ea88f-138">例については、 [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea88f-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea88f-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="ea88f-139">Requirements</span></span>
 <span data-ttu-id="ea88f-140">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea88f-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="ea88f-141">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="ea88f-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="ea88f-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ea88f-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ea88f-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea88f-143">See also</span></span>

- [<span data-ttu-id="ea88f-144">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ea88f-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
