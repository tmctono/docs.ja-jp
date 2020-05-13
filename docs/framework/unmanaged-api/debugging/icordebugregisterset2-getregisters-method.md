---
title: ICorDebugRegisterSet2::GetRegisters メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
ms.openlocfilehash: b7a356d80d63fae65191bbf4fc0a23d7e02004c9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378228"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="9b7b4-102">ICorDebugRegisterSet2::GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="9b7b4-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="9b7b4-103">指定されたビットマスクによって指定された各レジスタの値を取得します (コードが現在実行されているプラットフォーム用)。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b7b4-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b7b4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b7b4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b7b4-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="9b7b4-106">から配列のサイズ (バイト単位) `mask` 。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="9b7b4-107">からバイト配列。各ビットはレジスタに対応します。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="9b7b4-108">ビットが1の場合は、対応するレジスタの値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="9b7b4-109">から取得するレジスタ値の数。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="9b7b4-110">入出力オブジェクトの配列 `CORDB_REGISTER` 。各オブジェクトは、レジスタの値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b7b4-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b7b4-111">Remarks</span></span>  
 <span data-ttu-id="9b7b4-112">メソッドは、 `GetRegisters` マスクによって指定されたレジスタから値の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="9b7b4-113">配列に、マスクビットが設定されていないレジスタの値が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="9b7b4-114">したがって、配列のサイズは `regBuffer` マスク内の1の数と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="9b7b4-115">の値 `regCount` がマスクで示されているレジスタの数に対して小さすぎる場合、番号が大きいレジスタの値はセットから切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="9b7b4-116">`regCount`が大きすぎる場合、未使用の `regBuffer` 要素は変更されません。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="9b7b4-117">使用できないレジスタがマスクによって示されている場合、そのレジスタに対して不確定な値が返されます。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="9b7b4-118">メソッドは、 `ICorDebugRegisterSet2::GetRegisters` 64 を超えるレジスタを持つプラットフォームに必要です。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="9b7b4-119">たとえば、IA64 には128汎用レジスタと128浮動小数点レジスタがあるため、ビットマスクには64ビット以上のビットが必要です。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="9b7b4-120">X86 などのプラットフォームの場合と同様に、64以上のレジスタがない場合、メソッドは実際にはバイト配列のバイトをに変換し、次に、 `GetRegisters` `mask` `ULONG64` マスクを[ICorDebugRegisterSet::GetRegisters](icordebugregisterset-getregisters-method.md)取得する、は、のようにすることができます。 `ULONG64`</span><span class="sxs-lookup"><span data-stu-id="9b7b4-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b7b4-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="9b7b4-121">Requirements</span></span>  
 <span data-ttu-id="9b7b4-122">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b7b4-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b7b4-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b7b4-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b7b4-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b7b4-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b7b4-125">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b7b4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7b4-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b7b4-126">See also</span></span>

- [<span data-ttu-id="9b7b4-127">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b7b4-127">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="9b7b4-128">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b7b4-128">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
