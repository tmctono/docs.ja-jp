---
title: BeginMethodEnumeration 関数 (アンマネージ API リファレンス)
description: BeginMethodEnumeration 関数は、オブジェクトのメソッドの列挙を開始します。
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
ms.openlocfilehash: be1e86e0b760ab403cf42ac19da03f84769a85cf
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884424"
---
# <a name="beginmethodenumeration-function"></a><span data-ttu-id="829dd-103">BeginMethodEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="829dd-103">BeginMethodEnumeration function</span></span>
<span data-ttu-id="829dd-104">オブジェクトで使用できるメソッドの列挙を開始します。</span><span class="sxs-lookup"><span data-stu-id="829dd-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="829dd-105">構文</span><span class="sxs-lookup"><span data-stu-id="829dd-105">Syntax</span></span>  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="829dd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="829dd-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="829dd-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="829dd-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="829dd-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="829dd-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="829dd-109">からすべてのメソッドにゼロ (0)、または列挙体のスコープを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="829dd-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="829dd-110">次のフラグは、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="829dd-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="829dd-111">定数</span><span class="sxs-lookup"><span data-stu-id="829dd-111">Constant</span></span>  |<span data-ttu-id="829dd-112">Value</span><span class="sxs-lookup"><span data-stu-id="829dd-112">Value</span></span>  |<span data-ttu-id="829dd-113">説明</span><span class="sxs-lookup"><span data-stu-id="829dd-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="829dd-114">0x10</span><span class="sxs-lookup"><span data-stu-id="829dd-114">0x10</span></span> | <span data-ttu-id="829dd-115">列挙体は、クラス自体で定義されているメソッドに限定します。</span><span class="sxs-lookup"><span data-stu-id="829dd-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="829dd-116">0x20</span><span class="sxs-lookup"><span data-stu-id="829dd-116">0x20</span></span> | <span data-ttu-id="829dd-117">列挙型を基底クラスから継承されたプロパティに限定します。</span><span class="sxs-lookup"><span data-stu-id="829dd-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="829dd-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="829dd-118">Return value</span></span>

<span data-ttu-id="829dd-119">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="829dd-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="829dd-120">定数</span><span class="sxs-lookup"><span data-stu-id="829dd-120">Constant</span></span>  |<span data-ttu-id="829dd-121">Value</span><span class="sxs-lookup"><span data-stu-id="829dd-121">Value</span></span>  |<span data-ttu-id="829dd-122">説明</span><span class="sxs-lookup"><span data-stu-id="829dd-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="829dd-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="829dd-123">0x80041008</span></span> | <span data-ttu-id="829dd-124">`lEnnumFlags` が0以外で、が指定されたフラグの1つではありません。</span><span class="sxs-lookup"><span data-stu-id="829dd-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="829dd-125">0</span><span class="sxs-lookup"><span data-stu-id="829dd-125">0</span></span> | <span data-ttu-id="829dd-126">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="829dd-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="829dd-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="829dd-127">Remarks</span></span>

<span data-ttu-id="829dd-128">この関数は、 [IWbemClassObject:: BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="829dd-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="829dd-129">このメソッド呼び出しは、現在のオブジェクトがクラス定義の場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="829dd-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="829dd-130">インスタンスを指す[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)ポインターからは、メソッド操作を使用できません。</span><span class="sxs-lookup"><span data-stu-id="829dd-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="829dd-131">メソッドを列挙する順序は、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)の特定のインスタンスに対して不変であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="829dd-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="829dd-132">要件</span><span class="sxs-lookup"><span data-stu-id="829dd-132">Requirements</span></span>  
 <span data-ttu-id="829dd-133">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="829dd-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="829dd-134">**ヘッダー:** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="829dd-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="829dd-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="829dd-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="829dd-136">参照</span><span class="sxs-lookup"><span data-stu-id="829dd-136">See also</span></span>

- [<span data-ttu-id="829dd-137">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="829dd-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
