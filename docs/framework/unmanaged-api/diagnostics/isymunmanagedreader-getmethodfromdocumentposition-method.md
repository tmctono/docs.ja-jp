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
ms.openlocfilehash: 8015056b110fe8a5b5122b1bc81143980b780047
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614982"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="5c0f6-102">ISymUnmanagedReader::GetMethodFromDocumentPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="5c0f6-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="5c0f6-103">ドキュメント内の指定された位置にあるブレークポイントを含むメソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="5c0f6-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c0f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c0f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c0f6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c0f6-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="5c0f6-106">から指定されたドキュメント。</span><span class="sxs-lookup"><span data-stu-id="5c0f6-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="5c0f6-107">から指定したドキュメントの行。</span><span class="sxs-lookup"><span data-stu-id="5c0f6-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="5c0f6-108">から指定されたドキュメントの列。</span><span class="sxs-lookup"><span data-stu-id="5c0f6-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5c0f6-109">入出力ブレークポイントを含むメソッドを表す[ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md)オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5c0f6-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c0f6-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="5c0f6-110">Return Value</span></span>  
 <span data-ttu-id="5c0f6-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c0f6-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c0f6-112">要件</span><span class="sxs-lookup"><span data-stu-id="5c0f6-112">Requirements</span></span>  
 <span data-ttu-id="5c0f6-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="5c0f6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c0f6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c0f6-114">See also</span></span>

- [<span data-ttu-id="5c0f6-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c0f6-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
