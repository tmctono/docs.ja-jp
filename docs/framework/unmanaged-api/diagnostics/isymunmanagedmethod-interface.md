---
title: ISymUnmanagedMethod インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 1d3ccb2265f056d5776199d997dc067c8d5513e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448782"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="119b9-102">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="119b9-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="119b9-103">Represents a method within the symbol store.</span><span class="sxs-lookup"><span data-stu-id="119b9-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="119b9-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span><span class="sxs-lookup"><span data-stu-id="119b9-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="119b9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-105">Methods</span></span>  
  
|<span data-ttu-id="119b9-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-106">Method</span></span>|<span data-ttu-id="119b9-107">説明</span><span class="sxs-lookup"><span data-stu-id="119b9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="119b9-108">GetNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="119b9-109">Gets the namespace within which this method is defined.</span><span class="sxs-lookup"><span data-stu-id="119b9-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="119b9-110">GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="119b9-111">Returns the offset within this method that corresponds to a given position within a document.</span><span class="sxs-lookup"><span data-stu-id="119b9-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="119b9-112">GetParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="119b9-113">Gets the parameters for this method.</span><span class="sxs-lookup"><span data-stu-id="119b9-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="119b9-114">GetRanges メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="119b9-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span><span class="sxs-lookup"><span data-stu-id="119b9-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="119b9-116">GetRootScope メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="119b9-117">Gets the root lexical scope within this method.</span><span class="sxs-lookup"><span data-stu-id="119b9-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="119b9-118">このスコープはメソッド全体を囲みます。</span><span class="sxs-lookup"><span data-stu-id="119b9-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="119b9-119">GetScopeFromOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="119b9-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span><span class="sxs-lookup"><span data-stu-id="119b9-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="119b9-121">GetSequencePointCount メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="119b9-122">Gets the count of sequence points within this method.</span><span class="sxs-lookup"><span data-stu-id="119b9-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="119b9-123">GetSequencePoints メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="119b9-124">Gets all the sequence points within this method.</span><span class="sxs-lookup"><span data-stu-id="119b9-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="119b9-125">GetSourceStartEnd メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="119b9-126">Gets the start and end document positions for the source of this method.</span><span class="sxs-lookup"><span data-stu-id="119b9-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="119b9-127">GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="119b9-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="119b9-128">Returns the metadata token for this method.</span><span class="sxs-lookup"><span data-stu-id="119b9-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="119b9-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="119b9-129">Requirements</span></span>  
 <span data-ttu-id="119b9-130">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="119b9-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119b9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="119b9-131">See also</span></span>

- [<span data-ttu-id="119b9-132">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="119b9-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
