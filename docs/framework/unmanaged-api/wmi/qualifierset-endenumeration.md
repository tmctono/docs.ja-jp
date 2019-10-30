---
title: QualifierSet_EndEnumeration 関数 (アンマネージ API リファレンス)
description: QualifierSet_EndEnumeration 関数は、列挙体を終了します。
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
ms.openlocfilehash: 82627fa416f71e123ed2c03bae4584e4433310eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127291"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="ed12d-103">QualifierSet_EndEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="ed12d-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="ed12d-104">[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)関数の呼び出しで開始された列挙体を終了します。</span><span class="sxs-lookup"><span data-stu-id="ed12d-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ed12d-105">構文</span><span class="sxs-lookup"><span data-stu-id="ed12d-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="ed12d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ed12d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ed12d-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="ed12d-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="ed12d-108">から[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ed12d-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="ed12d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ed12d-109">Return value</span></span>

<span data-ttu-id="ed12d-110">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="ed12d-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="ed12d-111">定数</span><span class="sxs-lookup"><span data-stu-id="ed12d-111">Constant</span></span>  |<span data-ttu-id="ed12d-112">[値]</span><span class="sxs-lookup"><span data-stu-id="ed12d-112">Value</span></span>  |<span data-ttu-id="ed12d-113">説明</span><span class="sxs-lookup"><span data-stu-id="ed12d-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ed12d-114">0</span><span class="sxs-lookup"><span data-stu-id="ed12d-114">0</span></span> | <span data-ttu-id="ed12d-115">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="ed12d-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ed12d-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="ed12d-116">Remarks</span></span>

<span data-ttu-id="ed12d-117">この関数は、 [IWbemQualifierSet:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="ed12d-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="ed12d-118">この呼び出しは推奨されますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="ed12d-118">This call is recommended, but not required.</span></span> <span data-ttu-id="ed12d-119">列挙に関連付けられているリソースを直ちに解放します。</span><span class="sxs-lookup"><span data-stu-id="ed12d-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="ed12d-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="ed12d-120">Requirements</span></span>  

<span data-ttu-id="ed12d-121">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed12d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="ed12d-122">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="ed12d-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="ed12d-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ed12d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed12d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed12d-124">See also</span></span>

- [<span data-ttu-id="ed12d-125">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ed12d-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
