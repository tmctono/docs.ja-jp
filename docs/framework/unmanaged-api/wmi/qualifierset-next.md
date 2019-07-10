---
title: QualifierSet_Next 関数 (アンマネージ API リファレンス)
description: QualifierSet_Next 関数は、列挙体で、[次へ] 修飾子を取得します。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ac5cc8633881749bdc167e1b3925a83f7adf3b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760303"
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="fe57f-103">QualifierSet_Next 関数</span><span class="sxs-lookup"><span data-stu-id="fe57f-103">QualifierSet_Next function</span></span>
<span data-ttu-id="fe57f-104">[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 関数の呼び出しによって開始された列挙型内の次の修飾子が返されます。</span><span class="sxs-lookup"><span data-stu-id="fe57f-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fe57f-105">構文</span><span class="sxs-lookup"><span data-stu-id="fe57f-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="fe57f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe57f-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="fe57f-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="fe57f-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="fe57f-108">[in]ポインター、 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="fe57f-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="fe57f-109">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="fe57f-109">[in] Reserved.</span></span> <span data-ttu-id="fe57f-110">このパラメーターは、0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe57f-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="fe57f-111">[out]修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="fe57f-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="fe57f-112">場合`null`、このパラメーターは無視されます。 それ以外`pstrName`、有効なをポイントする必要がありますいない`BSTR`またはメモリ リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="fe57f-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="fe57f-113">かどうかは null でない関数は、常に割り当て、新しい`BSTR`を返す場合`WBEM_S_NO_ERROR`します。</span><span class="sxs-lookup"><span data-stu-id="fe57f-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="fe57f-114">[out]成功した場合、修飾子の値。</span><span class="sxs-lookup"><span data-stu-id="fe57f-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="fe57f-115">関数が失敗した場合、`VARIANT`によって示される`pVal`は変更されません。</span><span class="sxs-lookup"><span data-stu-id="fe57f-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="fe57f-116">このパラメーターが場合`null`パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="fe57f-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="fe57f-117">[out]修飾子のフレーバーを受信する長整数型へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe57f-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="fe57f-118">このパラメーターを指定できますフレーバー情報が望ましくない場合`null`します。</span><span class="sxs-lookup"><span data-stu-id="fe57f-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="fe57f-119">戻り値</span><span class="sxs-lookup"><span data-stu-id="fe57f-119">Return value</span></span>

<span data-ttu-id="fe57f-120">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="fe57f-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fe57f-121">定数</span><span class="sxs-lookup"><span data-stu-id="fe57f-121">Constant</span></span>  |<span data-ttu-id="fe57f-122">値</span><span class="sxs-lookup"><span data-stu-id="fe57f-122">Value</span></span>  |<span data-ttu-id="fe57f-123">説明</span><span class="sxs-lookup"><span data-stu-id="fe57f-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fe57f-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fe57f-124">0x80041008</span></span> | <span data-ttu-id="fe57f-125">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="fe57f-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="fe57f-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="fe57f-126">0x8004101d</span></span> | <span data-ttu-id="fe57f-127">呼び出し元が呼び出さなかった[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="fe57f-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fe57f-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fe57f-128">0x80041006</span></span> | <span data-ttu-id="fe57f-129">新しい列挙を開始するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="fe57f-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="fe57f-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="fe57f-130">0x40005</span></span> | <span data-ttu-id="fe57f-131">列挙型でその他の修飾子が残されません。</span><span class="sxs-lookup"><span data-stu-id="fe57f-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fe57f-132">0</span><span class="sxs-lookup"><span data-stu-id="fe57f-132">0</span></span> | <span data-ttu-id="fe57f-133">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="fe57f-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fe57f-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe57f-134">Remarks</span></span>

<span data-ttu-id="fe57f-135">この関数の呼び出しをラップする、 [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fe57f-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="fe57f-136">呼び出す、`QualifierSet_Next`関数の戻り値までのすべての修飾子を列挙するために繰り返し関数`WBEM_S_NO_MORE_DATA`します。</span><span class="sxs-lookup"><span data-stu-id="fe57f-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="fe57f-137">列挙体を早い段階を終了するには、呼び出し、 [QualifierSet_EndEnumeration](qualifierset-endenumeration.md)関数。</span><span class="sxs-lookup"><span data-stu-id="fe57f-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="fe57f-138">列挙時に返される修飾子の順序は定義されません。</span><span class="sxs-lookup"><span data-stu-id="fe57f-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="fe57f-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="fe57f-139">Requirements</span></span>  
 <span data-ttu-id="fe57f-140">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe57f-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe57f-141">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fe57f-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fe57f-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fe57f-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe57f-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe57f-143">See also</span></span>

- [<span data-ttu-id="fe57f-144">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="fe57f-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
