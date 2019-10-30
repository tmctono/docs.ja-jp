---
title: QualifierSet_GetNames 関数 (アンマネージ API リファレンス)
description: QualifierSet_GetNames 関数は、オブジェクトまたはプロパティから修飾子の名前を取得します。
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: bd0a67987dd8ffa825114726d066249aed40cf05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141694"
---
# <a name="qualifierset_getnames-function"></a><span data-ttu-id="ab458-103">QualifierSet_GetNames 関数</span><span class="sxs-lookup"><span data-stu-id="ab458-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="ab458-104">現在のオブジェクトまたはプロパティから使用可能な、すべての修飾子または特定の修飾子の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="ab458-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ab458-105">構文</span><span class="sxs-lookup"><span data-stu-id="ab458-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="ab458-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ab458-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="ab458-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="ab458-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="ab458-108">から[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ab458-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="ab458-109">から列挙に含める名前を指定する、次のいずれかのフラグまたは値。</span><span class="sxs-lookup"><span data-stu-id="ab458-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="ab458-110">定数</span><span class="sxs-lookup"><span data-stu-id="ab458-110">Constant</span></span>  |<span data-ttu-id="ab458-111">[値]</span><span class="sxs-lookup"><span data-stu-id="ab458-111">Value</span></span>  |<span data-ttu-id="ab458-112">説明</span><span class="sxs-lookup"><span data-stu-id="ab458-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="ab458-113">0</span><span class="sxs-lookup"><span data-stu-id="ab458-113">0</span></span> | <span data-ttu-id="ab458-114">すべての修飾子の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="ab458-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="ab458-115">0x10</span><span class="sxs-lookup"><span data-stu-id="ab458-115">0x10</span></span> | <span data-ttu-id="ab458-116">現在のプロパティまたはオブジェクトに固有の修飾子の名前のみを返します。</span><span class="sxs-lookup"><span data-stu-id="ab458-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="ab458-117">プロパティの場合: プロパティに固有の修飾子 (オーバーライドを含む) だけを返します。クラス定義から伝達された修飾子は返しません。</span><span class="sxs-lookup"><span data-stu-id="ab458-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="ab458-118">インスタンスの場合: インスタンス固有の修飾子名だけを返します。</span><span class="sxs-lookup"><span data-stu-id="ab458-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="ab458-119">クラスの場合: 派生するクラスに固有の修飾子だけを返します。</span><span class="sxs-lookup"><span data-stu-id="ab458-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="ab458-120">0x20</span><span class="sxs-lookup"><span data-stu-id="ab458-120">0x20</span></span> | <span data-ttu-id="ab458-121">別のオブジェクトから伝達された修飾子の名前のみを返します。</span><span class="sxs-lookup"><span data-stu-id="ab458-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="ab458-122">プロパティの場合: プロパティ自体からではなく、クラス定義からこのプロパティに反映された修飾子だけを返します。</span><span class="sxs-lookup"><span data-stu-id="ab458-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="ab458-123">インスタンスの場合: クラス定義から伝達された修飾子だけを返します。</span><span class="sxs-lookup"><span data-stu-id="ab458-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="ab458-124">クラスの場合: 親クラスから継承された修飾子名だけを返します。</span><span class="sxs-lookup"><span data-stu-id="ab458-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="ab458-125">入出力要求された名前を含む新しい `SAFEARRAY`。</span><span class="sxs-lookup"><span data-stu-id="ab458-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="ab458-126">配列には、0個の要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ab458-126">The array can have 0 elements.</span></span> <span data-ttu-id="ab458-127">エラーが発生した場合、新しい `SAFEARRAY` は返されません。</span><span class="sxs-lookup"><span data-stu-id="ab458-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="ab458-128">戻り値</span><span class="sxs-lookup"><span data-stu-id="ab458-128">Return value</span></span>

<span data-ttu-id="ab458-129">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab458-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ab458-130">定数</span><span class="sxs-lookup"><span data-stu-id="ab458-130">Constant</span></span>  |<span data-ttu-id="ab458-131">[値]</span><span class="sxs-lookup"><span data-stu-id="ab458-131">Value</span></span>  |<span data-ttu-id="ab458-132">説明</span><span class="sxs-lookup"><span data-stu-id="ab458-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ab458-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ab458-133">0x80041008</span></span> | <span data-ttu-id="ab458-134">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="ab458-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ab458-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ab458-135">0x80041006</span></span> | <span data-ttu-id="ab458-136">新しい列挙を開始するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="ab458-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ab458-137">0</span><span class="sxs-lookup"><span data-stu-id="ab458-137">0</span></span> | <span data-ttu-id="ab458-138">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="ab458-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ab458-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab458-139">Remarks</span></span>

<span data-ttu-id="ab458-140">この関数は、 [IWbemQualifierSet:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="ab458-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="ab458-141">修飾子名を取得したら、 [QualifierSet_Get](qualifierset-get.md)関数を呼び出すことによって、各修飾子に名前でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ab458-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="ab458-142">指定されたオブジェクトが修飾子を持たない場合のエラーではないため、関数が `WBEM_S_NO_ERROR`を返す場合でも、返される `pstrNames` 内の文字列の数は0になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab458-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="ab458-143">［要件］</span><span class="sxs-lookup"><span data-stu-id="ab458-143">Requirements</span></span>

<span data-ttu-id="ab458-144">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab458-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ab458-145">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="ab458-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ab458-146">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ab458-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ab458-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab458-147">See also</span></span>

- [<span data-ttu-id="ab458-148">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ab458-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
