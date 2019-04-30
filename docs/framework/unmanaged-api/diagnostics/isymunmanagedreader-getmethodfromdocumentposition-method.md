---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ed13397748b2668c275b221e38bd75c0dd37f03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969183"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="b66a8-102">ISymUnmanagedReader::GetMethodFromDocumentPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="b66a8-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="b66a8-103">ドキュメント内の指定位置にブレークポイントを含むメソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="b66a8-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b66a8-104">構文</span><span class="sxs-lookup"><span data-stu-id="b66a8-104">Syntax</span></span>  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b66a8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b66a8-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="b66a8-106">[in]指定されたドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="b66a8-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="b66a8-107">[in]指定されたドキュメントの行。</span><span class="sxs-lookup"><span data-stu-id="b66a8-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="b66a8-108">[in]指定されたドキュメントの列です。</span><span class="sxs-lookup"><span data-stu-id="b66a8-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b66a8-109">[out]アドレスへのポインターを[ISymUnmanagedMethod インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)ブレークポイントを含むメソッドを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b66a8-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b66a8-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="b66a8-110">Return Value</span></span>  
 <span data-ttu-id="b66a8-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="b66a8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b66a8-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="b66a8-112">Requirements</span></span>  
 <span data-ttu-id="b66a8-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b66a8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b66a8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b66a8-114">See also</span></span>

- [<span data-ttu-id="b66a8-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b66a8-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
