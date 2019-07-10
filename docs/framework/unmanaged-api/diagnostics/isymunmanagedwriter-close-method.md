---
title: ISymUnmanagedWriter::Close メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd7131c55f9c06a8fcfc0cad859c18e410169c78
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778199"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="ab3c5-102">ISymUnmanagedWriter::Close メソッド</span><span class="sxs-lookup"><span data-stu-id="ab3c5-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="ab3c5-103">シンボルをシンボル ストアにコミットした後は、シンボル ライターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ab3c5-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab3c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="ab3c5-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ab3c5-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="ab3c5-105">Return Value</span></span>  
 <span data-ttu-id="ab3c5-106">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ab3c5-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab3c5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab3c5-107">Remarks</span></span>  
 <span data-ttu-id="ab3c5-108">この呼び出しの後、シンボルのライターが、以降の更新は無効になります。</span><span class="sxs-lookup"><span data-stu-id="ab3c5-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="ab3c5-109">シンボルをコミットせずシンボル ライターを閉じるには使用、 [isymunmanagedwriter::abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="ab3c5-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab3c5-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab3c5-110">Requirements</span></span>  
 <span data-ttu-id="ab3c5-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ab3c5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab3c5-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab3c5-112">See also</span></span>

- [<span data-ttu-id="ab3c5-113">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab3c5-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
