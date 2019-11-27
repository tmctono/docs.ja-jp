---
title: ISymUnmanagedVariable インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: ee57ba14f048032e2cd9d0129089743c0f0304bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445982"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="a9bae-102">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9bae-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="a9bae-103">パラメーター、ローカル変数、フィールドなどの変数を表します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9bae-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-104">Methods</span></span>  
  
|<span data-ttu-id="a9bae-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-105">Method</span></span>|<span data-ttu-id="a9bae-106">説明</span><span class="sxs-lookup"><span data-stu-id="a9bae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9bae-107">GetAddressField1 メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="a9bae-108">この変数の最初のアドレスフィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="a9bae-109">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a9bae-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="a9bae-110">GetAddressField2 メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="a9bae-111">この変数の2番目のアドレスフィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="a9bae-112">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a9bae-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="a9bae-113">GetAddressField3 メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="a9bae-114">この変数の3番目のアドレスフィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="a9bae-115">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a9bae-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="a9bae-116">GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="a9bae-117">この変数のアドレスの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="a9bae-118">GetAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="a9bae-119">この変数の属性フラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="a9bae-120">GetEndOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="a9bae-121">親内のこの変数の終了オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="a9bae-122">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="a9bae-123">この変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="a9bae-124">GetSignature メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="a9bae-125">この変数のシグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="a9bae-126">GetStartOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="a9bae-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="a9bae-127">親内のこの変数の開始オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bae-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9bae-128">要件</span><span class="sxs-lookup"><span data-stu-id="a9bae-128">Requirements</span></span>  
 <span data-ttu-id="a9bae-129">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="a9bae-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9bae-130">参照</span><span class="sxs-lookup"><span data-stu-id="a9bae-130">See also</span></span>

- [<span data-ttu-id="a9bae-131">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9bae-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
