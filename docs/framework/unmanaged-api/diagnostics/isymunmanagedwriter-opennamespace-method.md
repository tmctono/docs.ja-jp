---
title: ISymUnmanagedWriter::OpenNamespace メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: acbd49de7362d9c05a609a2d870af100637e10ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427910"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="d26c9-102">ISymUnmanagedWriter::OpenNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="d26c9-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="d26c9-103">新しい名前空間を開きます。</span><span class="sxs-lookup"><span data-stu-id="d26c9-103">Opens a new namespace.</span></span> <span data-ttu-id="d26c9-104">名前空間を占有するメソッドまたは変数を定義する前に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d26c9-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="d26c9-105">名前空間は入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d26c9-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d26c9-106">構文</span><span class="sxs-lookup"><span data-stu-id="d26c9-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d26c9-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d26c9-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d26c9-108">から新しい名前空間の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d26c9-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d26c9-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="d26c9-109">Return Value</span></span>  
 <span data-ttu-id="d26c9-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d26c9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d26c9-111">要件</span><span class="sxs-lookup"><span data-stu-id="d26c9-111">Requirements</span></span>  
 <span data-ttu-id="d26c9-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="d26c9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d26c9-113">参照</span><span class="sxs-lookup"><span data-stu-id="d26c9-113">See also</span></span>

- [<span data-ttu-id="d26c9-114">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d26c9-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d26c9-115">CloseNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="d26c9-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
