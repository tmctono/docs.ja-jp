---
title: GetQualifierSet 関数 (アンマネージ API リファレンス)
description: GetQualifierSet 関数は、修飾子をクラスまたはインスタンスの設定を取得します。
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
ms.openlocfilehash: 75bf52fbf9552dc464d9c646f0a2b1bc01cf89c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193097"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="3b11e-103">GetQualifierSet 関数</span><span class="sxs-lookup"><span data-stu-id="3b11e-103">GetQualifierSet function</span></span>
<span data-ttu-id="3b11e-104">クラス インスタンスまたはクラス定義で設定された修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="3b11e-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="3b11e-105">構文</span><span class="sxs-lookup"><span data-stu-id="3b11e-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="3b11e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b11e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3b11e-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="3b11e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3b11e-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="3b11e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="3b11e-109">[out]クラスのオブジェクトの修飾子にアクセスできるインターフェイス ポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3b11e-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="3b11e-110">`ppQualSet` として `null` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b11e-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="3b11e-111">エラーが発生した、新しいオブジェクトは返されませんが、ポインターのままの場合変更されていません。</span><span class="sxs-lookup"><span data-stu-id="3b11e-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="3b11e-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="3b11e-112">Return value</span></span>

<span data-ttu-id="3b11e-113">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="3b11e-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3b11e-114">定数</span><span class="sxs-lookup"><span data-stu-id="3b11e-114">Constant</span></span>  |<span data-ttu-id="3b11e-115">値</span><span class="sxs-lookup"><span data-stu-id="3b11e-115">Value</span></span>  |<span data-ttu-id="3b11e-116">説明</span><span class="sxs-lookup"><span data-stu-id="3b11e-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="3b11e-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3b11e-117">0x80041001</span></span> | <span data-ttu-id="3b11e-118">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3b11e-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="3b11e-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3b11e-119">0x80041002</span></span> | <span data-ttu-id="3b11e-120">指定されたメソッドが存在しません。</span><span class="sxs-lookup"><span data-stu-id="3b11e-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3b11e-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3b11e-121">0x80041006</span></span> | <span data-ttu-id="3b11e-122">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="3b11e-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3b11e-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3b11e-123">0x80041008</span></span> | <span data-ttu-id="3b11e-124">パラメーターが`null`します。</span><span class="sxs-lookup"><span data-stu-id="3b11e-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3b11e-125">0</span><span class="sxs-lookup"><span data-stu-id="3b11e-125">0</span></span> | <span data-ttu-id="3b11e-126">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="3b11e-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3b11e-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b11e-127">Remarks</span></span>

<span data-ttu-id="3b11e-128">この関数の呼び出しをラップする、 [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)メソッド。</span><span class="sxs-lookup"><span data-stu-id="3b11e-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span> 

<span data-ttu-id="3b11e-129">[IWbemQualifierSet ポインター](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)により、呼び出し元を追加、編集、またはこれらの修飾子を削除します。</span><span class="sxs-lookup"><span data-stu-id="3b11e-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="3b11e-130">このような追加、編集、または削除された修飾子は、すべてのインスタンスまたはクラス定義に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3b11e-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b11e-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b11e-131">Requirements</span></span>  
<span data-ttu-id="3b11e-132">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b11e-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b11e-133">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3b11e-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3b11e-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3b11e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b11e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b11e-135">See also</span></span>

- [<span data-ttu-id="3b11e-136">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3b11e-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
