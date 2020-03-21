---
title: QualifierSet_Delete関数 (アンマネージ API リファレンス)
description: QualifierSet_Delete関数は、名前によって修飾子を削除します。
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0d2a02ba9d89ba16e776bb73563eaebf8a92f1fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174902"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="f44fd-103">QualifierSet_Delete 関数</span><span class="sxs-lookup"><span data-stu-id="f44fd-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="f44fd-104">名前によって指定した修飾子が削除されます。</span><span class="sxs-lookup"><span data-stu-id="f44fd-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f44fd-105">構文</span><span class="sxs-lookup"><span data-stu-id="f44fd-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="f44fd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f44fd-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f44fd-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="f44fd-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="f44fd-108">`ptr`[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f44fd-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="f44fd-109">`wszName`[in]削除する修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="f44fd-109">`wszName` [in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="f44fd-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="f44fd-110">Return value</span></span>

<span data-ttu-id="f44fd-111">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="f44fd-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f44fd-112">常時</span><span class="sxs-lookup"><span data-stu-id="f44fd-112">Constant</span></span>  |<span data-ttu-id="f44fd-113">Value</span><span class="sxs-lookup"><span data-stu-id="f44fd-113">Value</span></span>  |<span data-ttu-id="f44fd-114">説明</span><span class="sxs-lookup"><span data-stu-id="f44fd-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f44fd-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f44fd-115">0x80041008</span></span> | <span data-ttu-id="f44fd-116">`wszName` パラメーターが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="f44fd-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="f44fd-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="f44fd-117">0x80041016</span></span> | <span data-ttu-id="f44fd-118">この修飾子を削除することは無効です。</span><span class="sxs-lookup"><span data-stu-id="f44fd-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="f44fd-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f44fd-119">0x80041002</span></span> | <span data-ttu-id="f44fd-120">指定された修飾子が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="f44fd-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f44fd-121">0</span><span class="sxs-lookup"><span data-stu-id="f44fd-121">0</span></span> | <span data-ttu-id="f44fd-122">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="f44fd-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="f44fd-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="f44fd-123">0x40002</span></span> | <span data-ttu-id="f44fd-124">ローカルオーバーライドが削除され、親オブジェクトの元の修飾子がスコープを再開しました。</span><span class="sxs-lookup"><span data-stu-id="f44fd-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f44fd-125">解説</span><span class="sxs-lookup"><span data-stu-id="f44fd-125">Remarks</span></span>

<span data-ttu-id="f44fd-126">この関数は[、:D メソッド](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete)の呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="f44fd-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="f44fd-127">修飾子の伝達規則により、特定の修飾子が別のオブジェクトから継承され、現在のクラスまたはインスタンスでオーバーライドされただけである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f44fd-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="f44fd-128">この場合、メソッドは`QualifierSet_Delete`修飾子を元の継承値にリセットします。</span><span class="sxs-lookup"><span data-stu-id="f44fd-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="f44fd-129">この場合の関数は、状態コード`WBEM_S_RESET_TO_DEFAULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="f44fd-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="f44fd-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="f44fd-130">Requirements</span></span>  
 <span data-ttu-id="f44fd-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f44fd-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f44fd-132">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f44fd-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f44fd-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f44fd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f44fd-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="f44fd-134">See also</span></span>

- [<span data-ttu-id="f44fd-135">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f44fd-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
