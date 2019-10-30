---
title: QualifierSet_BeginEnumeration 関数 (アンマネージ API リファレンス)
description: QualifierSet_BeginEnumeration 関数は、オブジェクトの修飾子の列挙子をリセットします。
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 79edbd876fc9992f088b9adb159e005c735a72cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127323"
---
# <a name="qualifierset_beginenumeration-function"></a><span data-ttu-id="c237d-103">QualifierSet_BeginEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="c237d-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="c237d-104">オブジェクトの修飾子の列挙子が列挙型の先頭にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="c237d-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c237d-105">構文</span><span class="sxs-lookup"><span data-stu-id="c237d-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="c237d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c237d-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="c237d-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="c237d-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="c237d-108">から[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c237d-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="c237d-109">から列挙体に含める修飾子を指定する、「[解説](#remarks)」で説明されているフラグまたは値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="c237d-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="c237d-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="c237d-110">Return value</span></span>

<span data-ttu-id="c237d-111">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="c237d-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c237d-112">定数</span><span class="sxs-lookup"><span data-stu-id="c237d-112">Constant</span></span>  |<span data-ttu-id="c237d-113">[値]</span><span class="sxs-lookup"><span data-stu-id="c237d-113">Value</span></span>  |<span data-ttu-id="c237d-114">説明</span><span class="sxs-lookup"><span data-stu-id="c237d-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c237d-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c237d-115">0x80041008</span></span> | <span data-ttu-id="c237d-116">`lFlags` パラメーターが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="c237d-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="c237d-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="c237d-117">0x8004101d</span></span> | <span data-ttu-id="c237d-118">`QualifierSet_BeginEnumeration` の2回目の呼び出しが、 [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md)の介在する呼び出しなしで行われました。</span><span class="sxs-lookup"><span data-stu-id="c237d-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c237d-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c237d-119">0x80041006</span></span> | <span data-ttu-id="c237d-120">新しい列挙を開始するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="c237d-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c237d-121">0</span><span class="sxs-lookup"><span data-stu-id="c237d-121">0</span></span> | <span data-ttu-id="c237d-122">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="c237d-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="c237d-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="c237d-123">Remarks</span></span>

<span data-ttu-id="c237d-124">この関数は、 [IWbemQualifierSet:: BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="c237d-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="c237d-125">オブジェクトのすべての修飾子を列挙するには、 [QualifierSet_Next](qualifierset-next.md)の最初の呼び出しの前にこのメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c237d-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="c237d-126">修飾子が列挙される順序は、特定の列挙体に対して不変であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="c237d-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="c237d-127">`lEnumFlags` 引数として渡すことができるフラグは、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="c237d-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="c237d-128">定数</span><span class="sxs-lookup"><span data-stu-id="c237d-128">Constant</span></span>  |<span data-ttu-id="c237d-129">[値]</span><span class="sxs-lookup"><span data-stu-id="c237d-129">Value</span></span>  |<span data-ttu-id="c237d-130">説明</span><span class="sxs-lookup"><span data-stu-id="c237d-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="c237d-131">0</span><span class="sxs-lookup"><span data-stu-id="c237d-131">0</span></span> | <span data-ttu-id="c237d-132">すべての修飾子の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="c237d-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="c237d-133">0x10</span><span class="sxs-lookup"><span data-stu-id="c237d-133">0x10</span></span> | <span data-ttu-id="c237d-134">現在のプロパティまたはオブジェクトに固有の修飾子の名前のみを返します。</span><span class="sxs-lookup"><span data-stu-id="c237d-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="c237d-135">プロパティの場合: プロパティに固有の修飾子 (オーバーライドを含む) だけを返します。クラス定義から伝達された修飾子は返しません。</span><span class="sxs-lookup"><span data-stu-id="c237d-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="c237d-136">インスタンスの場合: インスタンス固有の修飾子名だけを返します。</span><span class="sxs-lookup"><span data-stu-id="c237d-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="c237d-137">クラスの場合: 派生するクラスに固有の修飾子だけを返します。</span><span class="sxs-lookup"><span data-stu-id="c237d-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="c237d-138">0x20</span><span class="sxs-lookup"><span data-stu-id="c237d-138">0x20</span></span> | <span data-ttu-id="c237d-139">別のオブジェクトから伝達された修飾子の名前のみを返します。</span><span class="sxs-lookup"><span data-stu-id="c237d-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="c237d-140">プロパティの場合: プロパティ自体からではなく、クラス定義からこのプロパティに反映された修飾子だけを返します。</span><span class="sxs-lookup"><span data-stu-id="c237d-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="c237d-141">インスタンスの場合: クラス定義から伝達された修飾子だけを返します。</span><span class="sxs-lookup"><span data-stu-id="c237d-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="c237d-142">クラスの場合: 親クラスから継承された修飾子名だけを返します。</span><span class="sxs-lookup"><span data-stu-id="c237d-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="c237d-143">［要件］</span><span class="sxs-lookup"><span data-stu-id="c237d-143">Requirements</span></span>

<span data-ttu-id="c237d-144">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c237d-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c237d-145">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="c237d-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="c237d-146">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c237d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c237d-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="c237d-147">See also</span></span>

- [<span data-ttu-id="c237d-148">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c237d-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
