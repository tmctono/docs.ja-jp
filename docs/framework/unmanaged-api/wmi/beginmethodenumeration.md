---
title: BeginMethodEnumeration 関数 (アンマネージ API リファレンス)
description: BeginMethodEnumeration 関数、オブジェクトのメソッドの列挙を開始します。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d6de2a5ff4d2743c7aca2e46b3af848138c15fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158783"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="41f99-103">BeginEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="41f99-103">BeginEnumeration function</span></span>
<span data-ttu-id="41f99-104">オブジェクトの使用可能なメソッドの列挙を開始します。</span><span class="sxs-lookup"><span data-stu-id="41f99-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="41f99-105">構文</span><span class="sxs-lookup"><span data-stu-id="41f99-105">Syntax</span></span>  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="41f99-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41f99-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="41f99-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="41f99-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="41f99-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="41f99-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="41f99-109">[in]ゼロ (0) のすべてのメソッド、または列挙体のスコープを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="41f99-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="41f99-110">次のフラグが定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="41f99-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="41f99-111">定数</span><span class="sxs-lookup"><span data-stu-id="41f99-111">Constant</span></span>  |<span data-ttu-id="41f99-112">値</span><span class="sxs-lookup"><span data-stu-id="41f99-112">Value</span></span>  |<span data-ttu-id="41f99-113">説明</span><span class="sxs-lookup"><span data-stu-id="41f99-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="41f99-114">0x10</span><span class="sxs-lookup"><span data-stu-id="41f99-114">0x10</span></span> | <span data-ttu-id="41f99-115">クラス自体で定義されているメソッドを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="41f99-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="41f99-116">0x20</span><span class="sxs-lookup"><span data-stu-id="41f99-116">0x20</span></span> | <span data-ttu-id="41f99-117">基底クラスから継承されるプロパティを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="41f99-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="41f99-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="41f99-118">Return value</span></span>

<span data-ttu-id="41f99-119">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="41f99-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="41f99-120">定数</span><span class="sxs-lookup"><span data-stu-id="41f99-120">Constant</span></span>  |<span data-ttu-id="41f99-121">値</span><span class="sxs-lookup"><span data-stu-id="41f99-121">Value</span></span>  |<span data-ttu-id="41f99-122">説明</span><span class="sxs-lookup"><span data-stu-id="41f99-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="41f99-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="41f99-123">0x80041008</span></span> | `lEnnumFlags` <span data-ttu-id="41f99-124">0 以外の場合し、指定したフラグではありません。</span><span class="sxs-lookup"><span data-stu-id="41f99-124">is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="41f99-125">0</span><span class="sxs-lookup"><span data-stu-id="41f99-125">0</span></span> | <span data-ttu-id="41f99-126">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="41f99-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="41f99-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="41f99-127">Remarks</span></span>

<span data-ttu-id="41f99-128">この関数の呼び出しをラップする、 [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration)メソッド。</span><span class="sxs-lookup"><span data-stu-id="41f99-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="41f99-129">このメソッドの呼び出しは、現在のオブジェクトがクラス定義である場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41f99-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="41f99-130">メソッドの操作をからご利用いただけません[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="41f99-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="41f99-131">特定のインスタンスのバリアントにメソッドが列挙される順序は保証[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)します。</span><span class="sxs-lookup"><span data-stu-id="41f99-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="41f99-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="41f99-132">Requirements</span></span>  
 <span data-ttu-id="41f99-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41f99-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41f99-134">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="41f99-134">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="41f99-135">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="41f99-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41f99-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="41f99-136">See also</span></span>

- [<span data-ttu-id="41f99-137">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="41f99-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
