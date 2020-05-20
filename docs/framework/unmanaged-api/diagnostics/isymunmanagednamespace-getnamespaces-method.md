---
title: ISymUnmanagedNamespace::GetNamespaces メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
ms.openlocfilehash: 48c50ac6be6d525676d85578e5a55a27104c180a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615099"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="733b6-102">ISymUnmanagedNamespace::GetNamespaces メソッド</span><span class="sxs-lookup"><span data-stu-id="733b6-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="733b6-103">この名前空間の子を取得します。</span><span class="sxs-lookup"><span data-stu-id="733b6-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="733b6-104">構文</span><span class="sxs-lookup"><span data-stu-id="733b6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="733b6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="733b6-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="733b6-106">から`ULONG32`配列のサイズを示す `namespaces` 。</span><span class="sxs-lookup"><span data-stu-id="733b6-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="733b6-107">入出力`ULONG32`名前空間を格納するために必要なバッファーのサイズ (文字数) を受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="733b6-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="733b6-108">入出力名前空間を格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="733b6-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="733b6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="733b6-109">Return Value</span></span>  
 <span data-ttu-id="733b6-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="733b6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="733b6-111">要件</span><span class="sxs-lookup"><span data-stu-id="733b6-111">Requirements</span></span>  
 <span data-ttu-id="733b6-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="733b6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="733b6-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="733b6-113">See also</span></span>

- [<span data-ttu-id="733b6-114">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="733b6-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
