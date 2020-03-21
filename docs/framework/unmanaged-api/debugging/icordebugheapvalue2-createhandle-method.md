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
ms.openlocfilehash: c7a1bf3cb10cbc8cdae2788b45e1badaf66a9dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178882"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="cae06-102">ICorDebugHeapValue2::CreateHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="cae06-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="cae06-103">この ICorDebugHeapValue2 オブジェクトによって表されるヒープ値の指定された型のハンドルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cae06-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae06-104">構文</span><span class="sxs-lookup"><span data-stu-id="cae06-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cae06-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cae06-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="cae06-106">[in]作成するハンドルの型を指定する列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="cae06-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="cae06-107">[アウト]このヒープ値の新しいハンドルを表すオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cae06-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cae06-108">解説</span><span class="sxs-lookup"><span data-stu-id="cae06-108">Remarks</span></span>  
 <span data-ttu-id="cae06-109">ハンドルはヒープ値に関連付けられているアプリケーション ドメインに作成され、アプリケーション ドメインがアンロードされると無効になります。</span><span class="sxs-lookup"><span data-stu-id="cae06-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="cae06-110">同じヒープ値に対してこの関数を複数回呼び出すと、複数のハンドルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cae06-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="cae06-111">ハンドルはガベージ コレクターのパフォーマンスに影響するため、デバッガーは、一度にアクティブになっている比較的少数のハンドル (約 256) に限定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cae06-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cae06-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="cae06-112">Requirements</span></span>  
 <span data-ttu-id="cae06-113">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cae06-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cae06-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cae06-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cae06-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cae06-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cae06-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cae06-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
