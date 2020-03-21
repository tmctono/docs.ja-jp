---
title: メソッドの削除関数 (アンマネージ API リファレンス)
description: DeleteMethod 関数は、指定されたメソッドを CIM クラス定義から削除します。
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 4059555d74c0b0f151332ddcf9faedecf238e795
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174993"
---
# <a name="deletemethod-function"></a><span data-ttu-id="0a923-103">DeleteMethod 関数</span><span class="sxs-lookup"><span data-stu-id="0a923-103">DeleteMethod function</span></span>
<span data-ttu-id="0a923-104">CIM クラス定義から指定したメソッドを削除します。</span><span class="sxs-lookup"><span data-stu-id="0a923-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0a923-105">構文</span><span class="sxs-lookup"><span data-stu-id="0a923-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="0a923-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a923-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0a923-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="0a923-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0a923-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0a923-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="0a923-109">[in]クラス テーブルから削除するメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="0a923-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="0a923-110">`wszName`は有効な`LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="0a923-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="0a923-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="0a923-111">Return value</span></span>

<span data-ttu-id="0a923-112">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="0a923-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0a923-113">常時</span><span class="sxs-lookup"><span data-stu-id="0a923-113">Constant</span></span>  |<span data-ttu-id="0a923-114">Value</span><span class="sxs-lookup"><span data-stu-id="0a923-114">Value</span></span>  |<span data-ttu-id="0a923-115">説明</span><span class="sxs-lookup"><span data-stu-id="0a923-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="0a923-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0a923-116">0x80041002</span></span> | <span data-ttu-id="0a923-117">指定されたメソッドは存在しません。</span><span class="sxs-lookup"><span data-stu-id="0a923-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0a923-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0a923-118">0x80041006</span></span> | <span data-ttu-id="0a923-119">操作を完了させるための十分なメモリがありません。</span><span class="sxs-lookup"><span data-stu-id="0a923-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0a923-120">0</span><span class="sxs-lookup"><span data-stu-id="0a923-120">0</span></span> | <span data-ttu-id="0a923-121">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="0a923-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="0a923-122">解説</span><span class="sxs-lookup"><span data-stu-id="0a923-122">Remarks</span></span>

<span data-ttu-id="0a923-123">この関数は、メソッドの呼び出し[:Dを](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod)ラップします。</span><span class="sxs-lookup"><span data-stu-id="0a923-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="0a923-124">メソッドの削除は、CIM インスタンスを指す[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)ポインターではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0a923-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a923-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="0a923-125">Requirements</span></span>  
 <span data-ttu-id="0a923-126">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a923-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a923-127">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0a923-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0a923-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0a923-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a923-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a923-129">See also</span></span>

- [<span data-ttu-id="0a923-130">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0a923-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
