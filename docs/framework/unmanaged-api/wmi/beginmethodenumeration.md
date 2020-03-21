---
title: メソッド列挙関数 (アンマネージ API リファレンス)
description: 関数は、オブジェクトのメソッドの列挙体を開始します。
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 876f5810fffab7fa98cd4d46715e13569ab95f6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175045"
---
# <a name="beginmethodenumeration-function"></a><span data-ttu-id="e993b-103">BeginMethodEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="e993b-103">BeginMethodEnumeration function</span></span>
<span data-ttu-id="e993b-104">オブジェクトに対して使用できるメソッドの列挙を開始します。</span><span class="sxs-lookup"><span data-stu-id="e993b-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e993b-105">構文</span><span class="sxs-lookup"><span data-stu-id="e993b-105">Syntax</span></span>  
  
```cpp
HRESULT BeginMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="e993b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e993b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e993b-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="e993b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e993b-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e993b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="e993b-109">[in]すべてのメソッドに対してゼロ (0) を指定するか、列挙のスコープを指定するフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="e993b-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="e993b-110">次のフラグは *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="e993b-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="e993b-111">常時</span><span class="sxs-lookup"><span data-stu-id="e993b-111">Constant</span></span>  |<span data-ttu-id="e993b-112">Value</span><span class="sxs-lookup"><span data-stu-id="e993b-112">Value</span></span>  |<span data-ttu-id="e993b-113">説明</span><span class="sxs-lookup"><span data-stu-id="e993b-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="e993b-114">0x10</span><span class="sxs-lookup"><span data-stu-id="e993b-114">0x10</span></span> | <span data-ttu-id="e993b-115">列挙型を、クラス自体で定義されているメソッドに制限します。</span><span class="sxs-lookup"><span data-stu-id="e993b-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="e993b-116">0x20</span><span class="sxs-lookup"><span data-stu-id="e993b-116">0x20</span></span> | <span data-ttu-id="e993b-117">列挙型を、基本クラスから継承されるプロパティに制限します。</span><span class="sxs-lookup"><span data-stu-id="e993b-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="e993b-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="e993b-118">Return value</span></span>

<span data-ttu-id="e993b-119">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="e993b-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e993b-120">常時</span><span class="sxs-lookup"><span data-stu-id="e993b-120">Constant</span></span>  |<span data-ttu-id="e993b-121">Value</span><span class="sxs-lookup"><span data-stu-id="e993b-121">Value</span></span>  |<span data-ttu-id="e993b-122">説明</span><span class="sxs-lookup"><span data-stu-id="e993b-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e993b-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e993b-123">0x80041008</span></span> | <span data-ttu-id="e993b-124">`lEnnumFlags`はゼロ以外であり、指定されたフラグの 1 つではありません。</span><span class="sxs-lookup"><span data-stu-id="e993b-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e993b-125">0</span><span class="sxs-lookup"><span data-stu-id="e993b-125">0</span></span> | <span data-ttu-id="e993b-126">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="e993b-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e993b-127">解説</span><span class="sxs-lookup"><span data-stu-id="e993b-127">Remarks</span></span>

<span data-ttu-id="e993b-128">この関数は、メソッドの呼び出し[をラップします](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration)。</span><span class="sxs-lookup"><span data-stu-id="e993b-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="e993b-129">このメソッド呼び出しは、現在のオブジェクトがクラス定義の場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e993b-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="e993b-130">メソッド操作は、インスタンスを指す[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)ポインターからは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e993b-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="e993b-131">メソッドが列挙される順序は、指定されたインスタンスの[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)に対して不変であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="e993b-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="e993b-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="e993b-132">Requirements</span></span>  
 <span data-ttu-id="e993b-133">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e993b-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e993b-134">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e993b-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e993b-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e993b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e993b-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e993b-136">See also</span></span>

- [<span data-ttu-id="e993b-137">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e993b-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
