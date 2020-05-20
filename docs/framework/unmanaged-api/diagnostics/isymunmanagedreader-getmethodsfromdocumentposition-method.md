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
ms.openlocfilehash: bba0fc039c403d45e8a5b60f2b0231eb24226280
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614956"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="5d05a-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="5d05a-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="5d05a-103">メソッドの配列を返します。各メソッドには、ドキュメント内の指定された位置にあるブレークポイントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d05a-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d05a-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d05a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5d05a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d05a-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="5d05a-106">から指定されたドキュメント。</span><span class="sxs-lookup"><span data-stu-id="5d05a-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="5d05a-107">から指定したドキュメントの行。</span><span class="sxs-lookup"><span data-stu-id="5d05a-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="5d05a-108">から指定されたドキュメントの列。</span><span class="sxs-lookup"><span data-stu-id="5d05a-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="5d05a-109">[in] `pRetVal` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="5d05a-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="5d05a-110">入出力配列で返された要素の数を受け取る変数へのポインター `pRetVal` 。</span><span class="sxs-lookup"><span data-stu-id="5d05a-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5d05a-111">入出力ポインターの配列。各ポインターは、ブレークポイントを含むメソッドを表す[ISymUnmanagedMethod](isymunmanagedmethod-interface.md)オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="5d05a-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d05a-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="5d05a-112">Return Value</span></span>  
 <span data-ttu-id="5d05a-113">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d05a-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d05a-114">要件</span><span class="sxs-lookup"><span data-stu-id="5d05a-114">Requirements</span></span>  
 <span data-ttu-id="5d05a-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="5d05a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d05a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d05a-116">See also</span></span>

- [<span data-ttu-id="5d05a-117">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5d05a-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
