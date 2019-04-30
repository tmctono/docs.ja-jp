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
ms.openlocfilehash: 878941f7af71fa5e3de8e38c4a68a66cb964983d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993786"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="d91de-102">ICorDebugType2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d91de-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="d91de-103">基本データ型または複合 (ユーザー定義) の型の型の識別子を取得する ICorDebugType インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="d91de-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d91de-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d91de-104">Methods</span></span>  
  
|<span data-ttu-id="d91de-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d91de-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="d91de-106">GetTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="d91de-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="d91de-107">取得、 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)この種類。</span><span class="sxs-lookup"><span data-stu-id="d91de-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d91de-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d91de-108">Remarks</span></span>  
 <span data-ttu-id="d91de-109">このインターフェイスは、ICorDebugType インターフェイスの論理拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="d91de-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d91de-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d91de-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d91de-111">例</span><span class="sxs-lookup"><span data-stu-id="d91de-111">Example</span></span>  
 <span data-ttu-id="d91de-112">次のコード フラグメントの使用を示しています、 [icordebugtype 2::gettypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d91de-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="d91de-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="d91de-113">Requirements</span></span>  
 <span data-ttu-id="d91de-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d91de-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d91de-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d91de-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d91de-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d91de-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d91de-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d91de-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91de-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d91de-118">See also</span></span>

- [<span data-ttu-id="d91de-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d91de-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
