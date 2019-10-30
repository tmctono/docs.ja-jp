---
title: QualifierSet_Next 関数 (アンマネージ API リファレンス)
description: QualifierSet_Next 関数は、列挙体の次の修飾子を取得します。
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
ms.openlocfilehash: c9c824b0158618848c13183d92f88604460d5099
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141722"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="f7371-103">QualifierSet_Next 関数</span><span class="sxs-lookup"><span data-stu-id="f7371-103">QualifierSet_Next function</span></span>
<span data-ttu-id="f7371-104">[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 関数の呼び出しによって開始された列挙型内の次の修飾子が返されます。</span><span class="sxs-lookup"><span data-stu-id="f7371-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f7371-105">構文</span><span class="sxs-lookup"><span data-stu-id="f7371-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="f7371-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7371-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="f7371-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="f7371-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="f7371-108">から[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f7371-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="f7371-109">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="f7371-109">[in] Reserved.</span></span> <span data-ttu-id="f7371-110">このパラメーターには0を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7371-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="f7371-111">入出力修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="f7371-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="f7371-112">`null`した場合、このパラメーターは無視されます。それ以外の場合は、`pstrName` が有効な `BSTR` を指していないか、メモリリークが発生します。</span><span class="sxs-lookup"><span data-stu-id="f7371-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="f7371-113">Null でない場合、関数は `WBEM_S_NO_ERROR`を返したときに常に新しい `BSTR` を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f7371-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="f7371-114">入出力成功した場合は、修飾子の値。</span><span class="sxs-lookup"><span data-stu-id="f7371-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="f7371-115">関数が失敗した場合、`pVal` が指す `VARIANT` は変更されません。</span><span class="sxs-lookup"><span data-stu-id="f7371-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="f7371-116">このパラメーターが `null`場合、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="f7371-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="f7371-117">入出力修飾子のフレーバーを受け取る LONG へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f7371-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="f7371-118">フレーバー情報が必要でない場合は、このパラメーターを `null`できます。</span><span class="sxs-lookup"><span data-stu-id="f7371-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="f7371-119">戻り値</span><span class="sxs-lookup"><span data-stu-id="f7371-119">Return value</span></span>

<span data-ttu-id="f7371-120">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7371-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f7371-121">定数</span><span class="sxs-lookup"><span data-stu-id="f7371-121">Constant</span></span>  |<span data-ttu-id="f7371-122">[値]</span><span class="sxs-lookup"><span data-stu-id="f7371-122">Value</span></span>  |<span data-ttu-id="f7371-123">説明</span><span class="sxs-lookup"><span data-stu-id="f7371-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f7371-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f7371-124">0x80041008</span></span> | <span data-ttu-id="f7371-125">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="f7371-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="f7371-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f7371-126">0x8004101d</span></span> | <span data-ttu-id="f7371-127">呼び出し元が[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)を呼び出しませんでした。</span><span class="sxs-lookup"><span data-stu-id="f7371-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f7371-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f7371-128">0x80041006</span></span> | <span data-ttu-id="f7371-129">新しい列挙を開始するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="f7371-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="f7371-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="f7371-130">0x40005</span></span> | <span data-ttu-id="f7371-131">列挙体にはそれ以上修飾子が残されていません。</span><span class="sxs-lookup"><span data-stu-id="f7371-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f7371-132">0</span><span class="sxs-lookup"><span data-stu-id="f7371-132">0</span></span> | <span data-ttu-id="f7371-133">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="f7371-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f7371-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="f7371-134">Remarks</span></span>

<span data-ttu-id="f7371-135">この関数は、 [IWbemQualifierSet:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="f7371-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="f7371-136">関数が `WBEM_S_NO_MORE_DATA`を返すまで、`QualifierSet_Next` 関数を繰り返し呼び出して、すべての修飾子を列挙します。</span><span class="sxs-lookup"><span data-stu-id="f7371-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="f7371-137">列挙型を早期に終了するには、 [QualifierSet_EndEnumeration](qualifierset-endenumeration.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f7371-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="f7371-138">列挙型の間に返される修飾子の順序は定義されていません。</span><span class="sxs-lookup"><span data-stu-id="f7371-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="f7371-139">［要件］</span><span class="sxs-lookup"><span data-stu-id="f7371-139">Requirements</span></span>  
 <span data-ttu-id="f7371-140">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7371-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7371-141">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="f7371-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f7371-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f7371-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7371-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7371-143">See also</span></span>

- [<span data-ttu-id="f7371-144">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f7371-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
