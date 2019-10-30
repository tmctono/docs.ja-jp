---
title: QualifierSet_Delete 関数 (アンマネージ API リファレンス)
description: QualifierSet_Delete 関数は、修飾子を名前で削除します。
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
ms.openlocfilehash: e7bedcb5c56f9976f8dfd2619081971075d0d809
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127295"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="20916-103">QualifierSet_Delete 関数</span><span class="sxs-lookup"><span data-stu-id="20916-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="20916-104">名前によって指定した修飾子が削除されます。</span><span class="sxs-lookup"><span data-stu-id="20916-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="20916-105">構文</span><span class="sxs-lookup"><span data-stu-id="20916-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="20916-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20916-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="20916-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="20916-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="20916-108">から[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="20916-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="20916-109">から削除する修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="20916-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="20916-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="20916-110">Return value</span></span>

<span data-ttu-id="20916-111">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="20916-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="20916-112">定数</span><span class="sxs-lookup"><span data-stu-id="20916-112">Constant</span></span>  |<span data-ttu-id="20916-113">[値]</span><span class="sxs-lookup"><span data-stu-id="20916-113">Value</span></span>  |<span data-ttu-id="20916-114">説明</span><span class="sxs-lookup"><span data-stu-id="20916-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="20916-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="20916-115">0x80041008</span></span> | <span data-ttu-id="20916-116">`wszName` パラメーターが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="20916-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="20916-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="20916-117">0x80041016</span></span> | <span data-ttu-id="20916-118">この修飾子の削除は無効です。</span><span class="sxs-lookup"><span data-stu-id="20916-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="20916-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="20916-119">0x80041002</span></span> | <span data-ttu-id="20916-120">指定された修飾子が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="20916-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="20916-121">0</span><span class="sxs-lookup"><span data-stu-id="20916-121">0</span></span> | <span data-ttu-id="20916-122">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="20916-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="20916-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="20916-123">0x40002</span></span> | <span data-ttu-id="20916-124">ローカルオーバーライドが削除され、親オブジェクトからの元の修飾子がスコープを再開しました。</span><span class="sxs-lookup"><span data-stu-id="20916-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="20916-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="20916-125">Remarks</span></span>

<span data-ttu-id="20916-126">この関数は、 [IWbemQualifierSet::D e)](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="20916-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="20916-127">修飾子の伝達規則により、特定の修飾子が別のオブジェクトから継承され、現在のクラスまたはインスタンスで単にオーバーライドされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20916-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="20916-128">この場合、`QualifierSet_Delete` メソッドは、修飾子を元の継承された値にリセットします。</span><span class="sxs-lookup"><span data-stu-id="20916-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="20916-129">この場合の関数は、状態コード `WBEM_S_RESET_TO_DEFAULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="20916-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="20916-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="20916-130">Requirements</span></span>  
 <span data-ttu-id="20916-131">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20916-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20916-132">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="20916-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="20916-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="20916-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20916-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="20916-134">See also</span></span>

- [<span data-ttu-id="20916-135">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="20916-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
