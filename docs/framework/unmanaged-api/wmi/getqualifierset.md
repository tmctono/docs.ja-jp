---
title: GetQualifierSet 関数 (アンマネージ API リファレンス)
description: GetQualifierSet 関数は、クラスまたはインスタンスに対して設定された修飾子を取得します。
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 845d5ea93a06859840c87c65b415ead0f846d538
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798466"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="00f0d-103">GetQualifierSet 関数</span><span class="sxs-lookup"><span data-stu-id="00f0d-103">GetQualifierSet function</span></span>
<span data-ttu-id="00f0d-104">クラス インスタンスまたはクラス定義で設定された修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="00f0d-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="00f0d-105">構文</span><span class="sxs-lookup"><span data-stu-id="00f0d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="00f0d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00f0d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="00f0d-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="00f0d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="00f0d-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="00f0d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="00f0d-109">入出力クラスオブジェクトの修飾子へのアクセスを許可するインターフェイスポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="00f0d-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="00f0d-110">`ppQualSet` として `null` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="00f0d-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="00f0d-111">エラーが発生した場合、新しいオブジェクトは返されず、ポインターは変更されません。</span><span class="sxs-lookup"><span data-stu-id="00f0d-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="00f0d-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="00f0d-112">Return value</span></span>

<span data-ttu-id="00f0d-113">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="00f0d-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="00f0d-114">定数</span><span class="sxs-lookup"><span data-stu-id="00f0d-114">Constant</span></span>  |<span data-ttu-id="00f0d-115">Value</span><span class="sxs-lookup"><span data-stu-id="00f0d-115">Value</span></span>  |<span data-ttu-id="00f0d-116">説明</span><span class="sxs-lookup"><span data-stu-id="00f0d-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="00f0d-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="00f0d-117">0x80041001</span></span> | <span data-ttu-id="00f0d-118">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="00f0d-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="00f0d-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="00f0d-119">0x80041002</span></span> | <span data-ttu-id="00f0d-120">指定されたメソッドは存在しません。</span><span class="sxs-lookup"><span data-stu-id="00f0d-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="00f0d-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="00f0d-121">0x80041006</span></span> | <span data-ttu-id="00f0d-122">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="00f0d-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="00f0d-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="00f0d-123">0x80041008</span></span> | <span data-ttu-id="00f0d-124">パラメーターが`null`です。</span><span class="sxs-lookup"><span data-stu-id="00f0d-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="00f0d-125">0</span><span class="sxs-lookup"><span data-stu-id="00f0d-125">0</span></span> | <span data-ttu-id="00f0d-126">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="00f0d-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="00f0d-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="00f0d-127">Remarks</span></span>

<span data-ttu-id="00f0d-128">この関数は、 [IWbemClassObject:: GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="00f0d-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span> 

<span data-ttu-id="00f0d-129">[IWbemQualifierSet ポインター](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)を使用すると、呼び出し元はこれらの修飾子を追加、編集、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="00f0d-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="00f0d-130">このように追加、編集、または削除された修飾子は、インスタンス全体またはクラス定義に適用されます。</span><span class="sxs-lookup"><span data-stu-id="00f0d-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="00f0d-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="00f0d-131">Requirements</span></span>  
<span data-ttu-id="00f0d-132">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00f0d-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00f0d-133">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="00f0d-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="00f0d-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="00f0d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f0d-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="00f0d-135">See also</span></span>

- [<span data-ttu-id="00f0d-136">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="00f0d-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
