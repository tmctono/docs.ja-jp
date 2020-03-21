---
title: 取得修飾子セット関数 (アンマネージ API リファレンス)
description: 関数は、クラスまたはインスタンスの修飾子セットを取得します。
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
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176774"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="57cef-103">GetQualifierSet 関数</span><span class="sxs-lookup"><span data-stu-id="57cef-103">GetQualifierSet function</span></span>
<span data-ttu-id="57cef-104">クラス インスタンスまたはクラス定義で設定された修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="57cef-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="57cef-105">構文</span><span class="sxs-lookup"><span data-stu-id="57cef-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="57cef-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="57cef-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="57cef-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="57cef-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="57cef-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="57cef-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="57cef-109">[アウト]クラス オブジェクトの修飾子へのアクセスを許可するインターフェイス ポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="57cef-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="57cef-110">`ppQualSet` として `null` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="57cef-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="57cef-111">エラーが発生した場合、新しいオブジェクトは返されず、ポインターは変更されません。</span><span class="sxs-lookup"><span data-stu-id="57cef-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="57cef-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="57cef-112">Return value</span></span>

<span data-ttu-id="57cef-113">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="57cef-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="57cef-114">常時</span><span class="sxs-lookup"><span data-stu-id="57cef-114">Constant</span></span>  |<span data-ttu-id="57cef-115">Value</span><span class="sxs-lookup"><span data-stu-id="57cef-115">Value</span></span>  |<span data-ttu-id="57cef-116">説明</span><span class="sxs-lookup"><span data-stu-id="57cef-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="57cef-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="57cef-117">0x80041001</span></span> | <span data-ttu-id="57cef-118">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="57cef-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="57cef-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="57cef-119">0x80041002</span></span> | <span data-ttu-id="57cef-120">指定されたメソッドは存在しません。</span><span class="sxs-lookup"><span data-stu-id="57cef-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="57cef-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="57cef-121">0x80041006</span></span> | <span data-ttu-id="57cef-122">メモリ不足のため、操作を完了できません。</span><span class="sxs-lookup"><span data-stu-id="57cef-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="57cef-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="57cef-123">0x80041008</span></span> | <span data-ttu-id="57cef-124">パラメータは`null`です。</span><span class="sxs-lookup"><span data-stu-id="57cef-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="57cef-125">0</span><span class="sxs-lookup"><span data-stu-id="57cef-125">0</span></span> | <span data-ttu-id="57cef-126">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="57cef-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="57cef-127">解説</span><span class="sxs-lookup"><span data-stu-id="57cef-127">Remarks</span></span>

<span data-ttu-id="57cef-128">この関数は、メソッドの呼び出し[を](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)ラップします。</span><span class="sxs-lookup"><span data-stu-id="57cef-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="57cef-129">[IWbemQualifierSet ポインター](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)を使用すると、呼び出し元がこれらの修飾子を追加、編集、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="57cef-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="57cef-130">このような追加、編集、または削除された修飾子は、インスタンスまたはクラス定義全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="57cef-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="57cef-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="57cef-131">Requirements</span></span>  
<span data-ttu-id="57cef-132">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57cef-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57cef-133">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="57cef-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="57cef-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="57cef-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57cef-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="57cef-135">See also</span></span>

- [<span data-ttu-id="57cef-136">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="57cef-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
