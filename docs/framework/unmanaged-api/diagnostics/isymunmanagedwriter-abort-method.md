---
title: ISymUnmanagedWriter::Abort メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 090183cad17aff6faf5e79639eadff086c1a26ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797463"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="9a89a-102">ISymUnmanagedWriter::Abort メソッド</span><span class="sxs-lookup"><span data-stu-id="9a89a-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="9a89a-103">シンボルをシンボル ストアにコミットせずには、シンボル ライターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9a89a-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="9a89a-104">この呼び出しの後、シンボルのライターが、以降の更新は無効になります。</span><span class="sxs-lookup"><span data-stu-id="9a89a-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="9a89a-105">コミットのシンボルをシンボル ライターを閉じるは、使用、 [isymunmanagedwriter::close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="9a89a-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a89a-106">構文</span><span class="sxs-lookup"><span data-stu-id="9a89a-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9a89a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="9a89a-107">Return Value</span></span>  
 <span data-ttu-id="9a89a-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="9a89a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a89a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a89a-109">Requirements</span></span>  
 <span data-ttu-id="9a89a-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9a89a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a89a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a89a-111">See also</span></span>

- [<span data-ttu-id="9a89a-112">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a89a-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
