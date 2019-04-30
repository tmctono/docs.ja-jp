---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8305d0a562fd90e3fae32e372b663ca3942d2a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940141"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="3efa4-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="3efa4-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="3efa4-103">非同期のグループを定義、現在のメソッドでの操作を待機します。</span><span class="sxs-lookup"><span data-stu-id="3efa4-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="3efa4-104">各 yield オフセットでは、潜在的な yield を識別する、await の戻り命令と一致します。</span><span class="sxs-lookup"><span data-stu-id="3efa4-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="3efa4-105">各`breakpointMethod` / `breakpointOffset`ペアによるメソッドが異なる可能性があるを非同期操作が再開されます。</span><span class="sxs-lookup"><span data-stu-id="3efa4-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3efa4-106">構文</span><span class="sxs-lookup"><span data-stu-id="3efa4-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3efa4-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3efa4-107">Parameters</span></span>  
  
|<span data-ttu-id="3efa4-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3efa4-108">Parameter</span></span>|<span data-ttu-id="3efa4-109">説明</span><span class="sxs-lookup"><span data-stu-id="3efa4-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="3efa4-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="3efa4-110">Return Value</span></span>  
 <span data-ttu-id="3efa4-111">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="3efa4-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3efa4-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="3efa4-112">Requirements</span></span>  
 <span data-ttu-id="3efa4-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3efa4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3efa4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3efa4-114">See also</span></span>

- [<span data-ttu-id="3efa4-115">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3efa4-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
