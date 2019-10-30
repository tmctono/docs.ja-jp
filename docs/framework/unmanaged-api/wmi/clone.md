---
title: Clone 関数 (アンマネージ API リファレンス)
description: Clone 関数は、現在のオブジェクトの完全な複製である新しいオブジェクトを返します。
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c8e7781a3efe7679ef2e05747862911db88bcc5f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141617"
---
# <a name="clone-function"></a><span data-ttu-id="3a0ec-103">Clone 関数</span><span class="sxs-lookup"><span data-stu-id="3a0ec-103">Clone function</span></span>
<span data-ttu-id="3a0ec-104">現在のオブジェクトの完全な複製である新しいオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3a0ec-105">構文</span><span class="sxs-lookup"><span data-stu-id="3a0ec-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="3a0ec-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a0ec-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3a0ec-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3a0ec-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="3a0ec-109">入出力完全な唯一の `ptr`である新しいオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="3a0ec-110">現在のオブジェクトのコピーを受け取った場合、この引数を `null` ことはできません。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="3a0ec-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a0ec-111">Return value</span></span>

<span data-ttu-id="3a0ec-112">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3a0ec-113">定数</span><span class="sxs-lookup"><span data-stu-id="3a0ec-113">Constant</span></span>  |<span data-ttu-id="3a0ec-114">[値]</span><span class="sxs-lookup"><span data-stu-id="3a0ec-114">Value</span></span>  |<span data-ttu-id="3a0ec-115">説明</span><span class="sxs-lookup"><span data-stu-id="3a0ec-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="3a0ec-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3a0ec-116">0x80041001</span></span> | <span data-ttu-id="3a0ec-117">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3a0ec-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3a0ec-118">0x80041008</span></span> | <span data-ttu-id="3a0ec-119">`null` がパラメーターとして指定されましたが、この使用法では有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3a0ec-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3a0ec-120">0x80041006</span></span> | <span data-ttu-id="3a0ec-121">オブジェクトを複製するのに十分なメモリがありません。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3a0ec-122">0</span><span class="sxs-lookup"><span data-stu-id="3a0ec-122">0</span></span> | <span data-ttu-id="3a0ec-123">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3a0ec-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a0ec-124">Remarks</span></span>

<span data-ttu-id="3a0ec-125">この関数は、 [IWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="3a0ec-126">複製されたオブジェクトは、参照カウントが1の COM オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a0ec-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="3a0ec-127">Requirements</span></span>  
 <span data-ttu-id="3a0ec-128">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0ec-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a0ec-129">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="3a0ec-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3a0ec-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3a0ec-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a0ec-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a0ec-131">See also</span></span>

- [<span data-ttu-id="3a0ec-132">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3a0ec-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
