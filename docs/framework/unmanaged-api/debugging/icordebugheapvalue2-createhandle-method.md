---
title: ICorDebugHeapValue2::CreateHandle メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 078dfd7162c250f0279b8bc372aeb39662aa0119
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779887"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="be715-102">ICorDebugHeapValue2::CreateHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="be715-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="be715-103">ICorDebugHeapValue2 オブジェクトによって表されるヒープ値の指定した型のハンドルを作成します。</span><span class="sxs-lookup"><span data-stu-id="be715-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be715-104">構文</span><span class="sxs-lookup"><span data-stu-id="be715-104">Syntax</span></span>  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be715-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be715-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="be715-106">[in]CorDebugHandleType 列挙型を作成するハンドルの種類を指定する値。</span><span class="sxs-lookup"><span data-stu-id="be715-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="be715-107">[out]このヒープ値に対して新しいハンドルを表す ICorDebugHandleValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="be715-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be715-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="be715-108">Remarks</span></span>  
 <span data-ttu-id="be715-109">ハンドルは、ヒープの値に関連付けられているアプリケーション ドメインでが作成され、アプリケーション ドメインがアンロードされると無効になります。</span><span class="sxs-lookup"><span data-stu-id="be715-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="be715-110">同じヒープ値に対してこの関数を複数の呼び出しでは、複数のハンドルを作成します。</span><span class="sxs-lookup"><span data-stu-id="be715-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="be715-111">ハンドルは、ガベージ コレクターのパフォーマンスに影響するために、一度にアクティブになっている (約 256) のハンドルの数を比較的小さなデバッガーに制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be715-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be715-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="be715-112">Requirements</span></span>  
 <span data-ttu-id="be715-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be715-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be715-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be715-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be715-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be715-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be715-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be715-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
