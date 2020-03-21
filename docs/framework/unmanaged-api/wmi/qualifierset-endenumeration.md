---
title: QualifierSet_EndEnumeration関数 (アンマネージ API リファレンス)
description: QualifierSet_EndEnumeration関数は、列挙を終了します。
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c606580ff2e02c5659c14b134b1a17a65651952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176748"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="6e4e1-103">QualifierSet_EndEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="6e4e1-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="6e4e1-104">[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)関数の呼び出しで始まる列挙を終了します。</span><span class="sxs-lookup"><span data-stu-id="6e4e1-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6e4e1-105">構文</span><span class="sxs-lookup"><span data-stu-id="6e4e1-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="6e4e1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e4e1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6e4e1-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="6e4e1-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="6e4e1-108">`ptr`[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6e4e1-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="6e4e1-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="6e4e1-109">Return value</span></span>

<span data-ttu-id="6e4e1-110">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e1-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="6e4e1-111">常時</span><span class="sxs-lookup"><span data-stu-id="6e4e1-111">Constant</span></span>  |<span data-ttu-id="6e4e1-112">Value</span><span class="sxs-lookup"><span data-stu-id="6e4e1-112">Value</span></span>  |<span data-ttu-id="6e4e1-113">説明</span><span class="sxs-lookup"><span data-stu-id="6e4e1-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6e4e1-114">0</span><span class="sxs-lookup"><span data-stu-id="6e4e1-114">0</span></span> | <span data-ttu-id="6e4e1-115">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="6e4e1-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6e4e1-116">解説</span><span class="sxs-lookup"><span data-stu-id="6e4e1-116">Remarks</span></span>

<span data-ttu-id="6e4e1-117">この関数は、メソッドの呼び出し[を](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration)ラップします。</span><span class="sxs-lookup"><span data-stu-id="6e4e1-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="6e4e1-118">この呼び出しは推奨されますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="6e4e1-118">This call is recommended, but not required.</span></span> <span data-ttu-id="6e4e1-119">列挙に関連付けられたリソースをすぐに解放します。</span><span class="sxs-lookup"><span data-stu-id="6e4e1-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e4e1-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="6e4e1-120">Requirements</span></span>  

<span data-ttu-id="6e4e1-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e4e1-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="6e4e1-122">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6e4e1-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="6e4e1-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6e4e1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4e1-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e4e1-124">See also</span></span>

- [<span data-ttu-id="6e4e1-125">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6e4e1-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
