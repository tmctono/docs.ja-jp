---
title: QualifierSet_Next関数 (アンマネージ API リファレンス)
description: QualifierSet_Next関数は、列挙体の次の修飾子を取得します。
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174876"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="7b26f-103">QualifierSet_Next 関数</span><span class="sxs-lookup"><span data-stu-id="7b26f-103">QualifierSet_Next function</span></span>
<span data-ttu-id="7b26f-104">[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 関数の呼び出しによって開始された列挙型内の次の修飾子が返されます。</span><span class="sxs-lookup"><span data-stu-id="7b26f-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7b26f-105">構文</span><span class="sxs-lookup"><span data-stu-id="7b26f-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="7b26f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b26f-106">Parameters</span></span>

<span data-ttu-id="7b26f-107">`vFunc`[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="7b26f-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="7b26f-108">`ptr`[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7b26f-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="7b26f-109">`lFlags`[in]予約。</span><span class="sxs-lookup"><span data-stu-id="7b26f-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="7b26f-110">このパラメーターは 0 でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7b26f-110">This parameter must be 0.</span></span>

<span data-ttu-id="7b26f-111">`pstrName`[アウト]修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="7b26f-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="7b26f-112">の`null`場合、このパラメータは無視されます。それ以外`pstrName`の場合は、有効`BSTR`なメモリ リークが発生することを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b26f-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="7b26f-113">null でない場合、関数は戻るときに`BSTR``WBEM_S_NO_ERROR`常に新しいを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7b26f-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="7b26f-114">`pVal`[アウト]成功した場合は、修飾子の値。</span><span class="sxs-lookup"><span data-stu-id="7b26f-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="7b26f-115">関数が失敗した場合、`VARIANT`指すが`pVal`変更されません。</span><span class="sxs-lookup"><span data-stu-id="7b26f-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="7b26f-116">このパラメーターが`null`の場合、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="7b26f-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="7b26f-117">`plFlavor`[アウト]修飾子のフレーバーを受け取る LONG へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7b26f-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="7b26f-118">フレーバー情報が必要ない場合、このパラメーターは`null`.</span><span class="sxs-lookup"><span data-stu-id="7b26f-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="7b26f-119">戻り値</span><span class="sxs-lookup"><span data-stu-id="7b26f-119">Return value</span></span>

<span data-ttu-id="7b26f-120">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="7b26f-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7b26f-121">常時</span><span class="sxs-lookup"><span data-stu-id="7b26f-121">Constant</span></span>  |<span data-ttu-id="7b26f-122">Value</span><span class="sxs-lookup"><span data-stu-id="7b26f-122">Value</span></span>  |<span data-ttu-id="7b26f-123">説明</span><span class="sxs-lookup"><span data-stu-id="7b26f-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7b26f-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7b26f-124">0x80041008</span></span> | <span data-ttu-id="7b26f-125">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="7b26f-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="7b26f-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="7b26f-126">0x8004101d</span></span> | <span data-ttu-id="7b26f-127">呼び出し元は[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)を呼び出しませんでした。</span><span class="sxs-lookup"><span data-stu-id="7b26f-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7b26f-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7b26f-128">0x80041006</span></span> | <span data-ttu-id="7b26f-129">メモリ不足で新しい列挙を開始できません。</span><span class="sxs-lookup"><span data-stu-id="7b26f-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="7b26f-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="7b26f-130">0x40005</span></span> | <span data-ttu-id="7b26f-131">列挙体に修飾子が残っていません。</span><span class="sxs-lookup"><span data-stu-id="7b26f-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7b26f-132">0</span><span class="sxs-lookup"><span data-stu-id="7b26f-132">0</span></span> | <span data-ttu-id="7b26f-133">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="7b26f-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7b26f-134">解説</span><span class="sxs-lookup"><span data-stu-id="7b26f-134">Remarks</span></span>

<span data-ttu-id="7b26f-135">この関数は[、IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)メソッドへの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="7b26f-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="7b26f-136">関数が`QualifierSet_Next`戻`WBEM_S_NO_MORE_DATA`るまで、関数を繰り返し呼び出してすべての修飾子を列挙します。</span><span class="sxs-lookup"><span data-stu-id="7b26f-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="7b26f-137">列挙を早期に終了するには[、QualifierSet_EndEnumeration](qualifierset-endenumeration.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7b26f-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="7b26f-138">列挙時に返される修飾子の順序は未定義です。</span><span class="sxs-lookup"><span data-stu-id="7b26f-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="7b26f-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="7b26f-139">Requirements</span></span>  
 <span data-ttu-id="7b26f-140">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b26f-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b26f-141">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7b26f-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7b26f-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7b26f-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b26f-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b26f-143">See also</span></span>

- [<span data-ttu-id="7b26f-144">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7b26f-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
