---
title: EndEnumeration 関数 (アンマネージ API リファレンス)
description: EndEnumeration 関数は、列挙を終了します。
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65904da9efea90d31960d71ae0da8c81dffeccf1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000468"
---
# <a name="endenumeration-function"></a><span data-ttu-id="dbf86-103">EndEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="dbf86-103">EndEnumeration function</span></span>

<span data-ttu-id="dbf86-104">呼び出しで開始した、列挙体シーケンスの終了、 [BeginEnumeration 関数](beginenumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="dbf86-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="dbf86-105">構文</span><span class="sxs-lookup"><span data-stu-id="dbf86-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="dbf86-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dbf86-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="dbf86-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="dbf86-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="dbf86-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="dbf86-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="dbf86-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="dbf86-109">Return value</span></span>

<span data-ttu-id="dbf86-110">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="dbf86-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="dbf86-111">定数</span><span class="sxs-lookup"><span data-stu-id="dbf86-111">Constant</span></span>  |<span data-ttu-id="dbf86-112">値</span><span class="sxs-lookup"><span data-stu-id="dbf86-112">Value</span></span>  |<span data-ttu-id="dbf86-113">説明</span><span class="sxs-lookup"><span data-stu-id="dbf86-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="dbf86-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="dbf86-114">0x80041001</span></span> | <span data-ttu-id="dbf86-115">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="dbf86-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="dbf86-116">0</span><span class="sxs-lookup"><span data-stu-id="dbf86-116">0</span></span> | <span data-ttu-id="dbf86-117">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="dbf86-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="dbf86-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="dbf86-118">Remarks</span></span>

<span data-ttu-id="dbf86-119">この関数の呼び出しをラップする、 [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)メソッド。</span><span class="sxs-lookup"><span data-stu-id="dbf86-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="dbf86-120">呼び出し、`EndEnumeration`関数は必要ありませんが、列挙体に関連付けられているリソースを解放するためお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbf86-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="dbf86-121">ただし、リソースは、次の列挙を開始またはオブジェクトがリリースされたときに、自動的に解放します。</span><span class="sxs-lookup"><span data-stu-id="dbf86-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="dbf86-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="dbf86-122">Requirements</span></span>

<span data-ttu-id="dbf86-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbf86-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="dbf86-124">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="dbf86-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="dbf86-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dbf86-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="dbf86-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbf86-126">See also</span></span>

- [<span data-ttu-id="dbf86-127">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="dbf86-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)