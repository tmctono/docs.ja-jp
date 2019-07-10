---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e283bea2ce2f4b2e17da6e8dcb85165d3c4d6693
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776964"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="0e91b-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="0e91b-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="0e91b-103">メソッドのドキュメントで指定された位置にブレークポイントを含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="0e91b-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e91b-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e91b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e91b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e91b-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="0e91b-106">[in]指定されたドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="0e91b-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="0e91b-107">[in]指定されたドキュメントの行。</span><span class="sxs-lookup"><span data-stu-id="0e91b-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="0e91b-108">[in]指定されたドキュメントの列です。</span><span class="sxs-lookup"><span data-stu-id="0e91b-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="0e91b-109">[in] `pRetVal` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="0e91b-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="0e91b-110">[out]返される要素の数を受け取る変数へのポインター、`pRetVal`配列。</span><span class="sxs-lookup"><span data-stu-id="0e91b-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0e91b-111">[out]それぞれが指すポインターの配列、 [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)ブレークポイントを含むメソッドを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0e91b-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e91b-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="0e91b-112">Return Value</span></span>  
 <span data-ttu-id="0e91b-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="0e91b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e91b-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="0e91b-114">Requirements</span></span>  
 <span data-ttu-id="0e91b-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0e91b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e91b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e91b-116">See also</span></span>

- [<span data-ttu-id="0e91b-117">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e91b-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
