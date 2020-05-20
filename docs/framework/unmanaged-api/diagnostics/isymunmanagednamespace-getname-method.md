---
title: ISymUnmanagedNamespace::GetName メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: 84b2f1226c84713483499c7ff777838058cb0f95
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615112"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="14047-102">ISymUnmanagedNamespace::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="14047-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="14047-103">この名前空間の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="14047-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14047-104">構文</span><span class="sxs-lookup"><span data-stu-id="14047-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14047-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="14047-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="14047-106">から`ULONG32`バッファーのサイズを示す `szName` 。</span><span class="sxs-lookup"><span data-stu-id="14047-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="14047-107">入出力`ULONG32`Null 終了を含む、名前空間の名前を格納するために必要なバッファーのサイズ (文字数) を受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="14047-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="14047-108">入出力名前空間の名前を格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="14047-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14047-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="14047-109">Return Value</span></span>  
 <span data-ttu-id="14047-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="14047-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14047-111">要件</span><span class="sxs-lookup"><span data-stu-id="14047-111">Requirements</span></span>  
 <span data-ttu-id="14047-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="14047-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14047-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="14047-113">See also</span></span>

- [<span data-ttu-id="14047-114">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14047-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
