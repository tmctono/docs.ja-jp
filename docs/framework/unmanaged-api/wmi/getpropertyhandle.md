---
title: GetPropertyHandle 関数 (アンマネージ API リファレンス)
description: GetPropertyHandle 関数は、プロパティを識別する一意のハンドルを返します。
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d72b0da43971a74a08a249b19dfc0d446eeb5e6a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798541"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="6ecef-103">GetPropertyHandle 関数</span><span class="sxs-lookup"><span data-stu-id="6ecef-103">GetPropertyHandle function</span></span>

<span data-ttu-id="6ecef-104">プロパティを識別する一意のハンドルが返されます。</span><span class="sxs-lookup"><span data-stu-id="6ecef-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6ecef-105">構文</span><span class="sxs-lookup"><span data-stu-id="6ecef-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="6ecef-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ecef-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="6ecef-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="6ecef-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="6ecef-108">から[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6ecef-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="6ecef-109">からプロパティ名を含む、UTF16 でエンコードされた文字の null で終わる文字列。</span><span class="sxs-lookup"><span data-stu-id="6ecef-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="6ecef-110">入出力プロパティの CIM 型[`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration)を表す列挙体メンバーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6ecef-110">[out] A pointer to a [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="6ecef-111">入出力プロパティハンドルを格納している整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6ecef-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="6ecef-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="6ecef-112">Return value</span></span>

<span data-ttu-id="6ecef-113">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6ecef-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6ecef-114">定数</span><span class="sxs-lookup"><span data-stu-id="6ecef-114">Constant</span></span>  |<span data-ttu-id="6ecef-115">Value</span><span class="sxs-lookup"><span data-stu-id="6ecef-115">Value</span></span>  |<span data-ttu-id="6ecef-116">説明</span><span class="sxs-lookup"><span data-stu-id="6ecef-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="6ecef-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="6ecef-117">0x80041002</span></span> | <span data-ttu-id="6ecef-118">指定されたプロパティ名が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="6ecef-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6ecef-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6ecef-119">0x80041008</span></span> | <span data-ttu-id="6ecef-120">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="6ecef-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="6ecef-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="6ecef-121">0x8004100c</span></span> | <span data-ttu-id="6ecef-122">要求されたプロパティの型`CIM_OBJECT`は`CIM_ARRAY`またはです。</span><span class="sxs-lookup"><span data-stu-id="6ecef-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6ecef-123">0</span><span class="sxs-lookup"><span data-stu-id="6ecef-123">0</span></span> | <span data-ttu-id="6ecef-124">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="6ecef-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="6ecef-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ecef-125">Remarks</span></span>

<span data-ttu-id="6ecef-126">この関数は、 [IWbemClassObject:: GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="6ecef-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="6ecef-127">このハンドルを使用すると、 [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)メソッドを使用してプロパティ値の読み取りまたは書き込みを行うときに、プロパティを識別できます。</span><span class="sxs-lookup"><span data-stu-id="6ecef-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="6ecef-128">ハンドルは、および`CIM_OBJECT` `CIM_ARRAY`以外のすべてのデータ型のプロパティに対して取得できます。</span><span class="sxs-lookup"><span data-stu-id="6ecef-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="6ecef-129">返されるハンドルは、クラスのすべてのインスタンスで機能します。</span><span class="sxs-lookup"><span data-stu-id="6ecef-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ecef-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="6ecef-130">Requirements</span></span>

<span data-ttu-id="6ecef-131">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ecef-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="6ecef-132">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="6ecef-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="6ecef-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6ecef-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6ecef-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ecef-134">See also</span></span>

- [<span data-ttu-id="6ecef-135">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6ecef-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
