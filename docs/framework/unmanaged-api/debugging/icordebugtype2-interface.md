---
title: ICorDebugType2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2f2c1e4c95c61eab4c9da6103d4ac479b4bbdb4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936055"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="7051f-102">ICorDebugType2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7051f-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="7051f-103">によって、テキスト型または複合型 (ユーザー定義型) の型識別子を取得するために、を拡張します。</span><span class="sxs-lookup"><span data-stu-id="7051f-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7051f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7051f-104">Methods</span></span>  
  
|<span data-ttu-id="7051f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7051f-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="7051f-106">GetTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="7051f-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="7051f-107">この型の[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)を取得します。</span><span class="sxs-lookup"><span data-stu-id="7051f-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7051f-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="7051f-108">Remarks</span></span>  
 <span data-ttu-id="7051f-109">このインターフェイスは、テキストの型インターフェイスの論理上の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="7051f-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7051f-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7051f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7051f-111">例</span><span class="sxs-lookup"><span data-stu-id="7051f-111">Example</span></span>  
 <span data-ttu-id="7051f-112">次のコードフラグメントは、 [ICorDebugType2:: GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)メソッドの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7051f-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="7051f-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="7051f-113">Requirements</span></span>  
 <span data-ttu-id="7051f-114">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7051f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7051f-115">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7051f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7051f-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="7051f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7051f-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7051f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7051f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7051f-118">See also</span></span>

- [<span data-ttu-id="7051f-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7051f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
