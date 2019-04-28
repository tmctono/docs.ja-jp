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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 712eca7f3f9fec9c81e638802f5a664ec6469d53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797483"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="4699a-102">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4699a-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="4699a-103">パラメーター、ローカル変数またはフィールドなどの変数を表します。</span><span class="sxs-lookup"><span data-stu-id="4699a-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4699a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-104">Methods</span></span>  
  
|<span data-ttu-id="4699a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-105">Method</span></span>|<span data-ttu-id="4699a-106">説明</span><span class="sxs-lookup"><span data-stu-id="4699a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4699a-107">GetAddressField1 メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="4699a-108">この変数の最初のアドレス フィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="4699a-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="4699a-109">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4699a-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="4699a-110">GetAddressField2 メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="4699a-111">この変数の 2 番目のアドレス フィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="4699a-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="4699a-112">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4699a-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="4699a-113">GetAddressField3 メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="4699a-114">この変数の 3 番目のアドレス フィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="4699a-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="4699a-115">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4699a-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="4699a-116">GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="4699a-117">この変数のアドレスの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="4699a-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="4699a-118">GetAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="4699a-119">この変数の属性フラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="4699a-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="4699a-120">GetEndOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="4699a-121">親内でこの変数の終了オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="4699a-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="4699a-122">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="4699a-123">この変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="4699a-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="4699a-124">GetSignature メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="4699a-125">この変数のシグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="4699a-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="4699a-126">GetStartOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="4699a-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="4699a-127">この変数の親内の開始オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="4699a-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4699a-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="4699a-128">Requirements</span></span>  
 <span data-ttu-id="4699a-129">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4699a-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4699a-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="4699a-130">See also</span></span>

- [<span data-ttu-id="4699a-131">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4699a-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
