---
title: ISymUnmanagedReader2::GetMethodsInDocument メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
ms.openlocfilehash: 70c1d87ae32fb70f8d9f6e32b527394022459526
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446430"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="aa3dd-102">ISymUnmanagedReader2::GetMethodsInDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="aa3dd-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="aa3dd-103">指定されたドキュメントに行情報が含まれるすべてのメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="aa3dd-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa3dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="aa3dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa3dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa3dd-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="aa3dd-106">からドキュメントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="aa3dd-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="aa3dd-107">から`pRetVal` 配列のサイズを示す `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="aa3dd-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="aa3dd-108">入出力メソッドを格納するために必要なバッファーのサイズを受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="aa3dd-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="aa3dd-109">入出力メソッドを受け取るバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="aa3dd-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa3dd-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="aa3dd-110">Return Value</span></span>  
 <span data-ttu-id="aa3dd-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="aa3dd-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa3dd-112">要件</span><span class="sxs-lookup"><span data-stu-id="aa3dd-112">Requirements</span></span>  
 <span data-ttu-id="aa3dd-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="aa3dd-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa3dd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa3dd-114">See also</span></span>

- [<span data-ttu-id="aa3dd-115">ISymUnmanagedReader2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa3dd-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
