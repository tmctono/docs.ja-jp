---
title: EndEnumeration 関数 (アンマネージ API リファレンス)
description: EndEnumeration 関数は、列挙体を終了します。
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
ms.openlocfilehash: 0065dcd25430e102b965d5598c7e9a04c7857eb3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798814"
---
# <a name="endenumeration-function"></a><span data-ttu-id="58e8e-103">EndEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="58e8e-103">EndEnumeration function</span></span>

<span data-ttu-id="58e8e-104">[Beginenumeration 関数](beginenumeration.md)の呼び出しで開始された列挙シーケンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="58e8e-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="58e8e-105">構文</span><span class="sxs-lookup"><span data-stu-id="58e8e-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="58e8e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58e8e-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="58e8e-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="58e8e-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="58e8e-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="58e8e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="58e8e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="58e8e-109">Return value</span></span>

<span data-ttu-id="58e8e-110">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="58e8e-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="58e8e-111">定数</span><span class="sxs-lookup"><span data-stu-id="58e8e-111">Constant</span></span>  |<span data-ttu-id="58e8e-112">Value</span><span class="sxs-lookup"><span data-stu-id="58e8e-112">Value</span></span>  |<span data-ttu-id="58e8e-113">説明</span><span class="sxs-lookup"><span data-stu-id="58e8e-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="58e8e-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="58e8e-114">0x80041001</span></span> | <span data-ttu-id="58e8e-115">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="58e8e-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="58e8e-116">0</span><span class="sxs-lookup"><span data-stu-id="58e8e-116">0</span></span> | <span data-ttu-id="58e8e-117">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="58e8e-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="58e8e-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="58e8e-118">Remarks</span></span>

<span data-ttu-id="58e8e-119">この関数は、 [IWbemClassObject:: EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="58e8e-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="58e8e-120">`EndEnumeration`関数を呼び出す必要はありませんが、列挙型に関連付けられているリソースを解放するため、この関数を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58e8e-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="58e8e-121">ただし、次の列挙が開始されるか、オブジェクトが解放されると、リソースは自動的に割り当て解除されます。</span><span class="sxs-lookup"><span data-stu-id="58e8e-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="58e8e-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="58e8e-122">Requirements</span></span>

<span data-ttu-id="58e8e-123">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e8e-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="58e8e-124">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="58e8e-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="58e8e-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="58e8e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="58e8e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="58e8e-126">See also</span></span>

- [<span data-ttu-id="58e8e-127">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="58e8e-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
