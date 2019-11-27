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
ms.openlocfilehash: 43f32ac85bebc12d0a9253205aae3f1de0dc9e5b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433964"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="87bed-102">ISymUnmanagedNamespace::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="87bed-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="87bed-103">この名前空間の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="87bed-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87bed-104">構文</span><span class="sxs-lookup"><span data-stu-id="87bed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87bed-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87bed-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="87bed-106">から`szName` バッファーのサイズを示す `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="87bed-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="87bed-107">入出力Null 終了を含む、名前空間の名前を格納するために必要なバッファーのサイズ (文字数) を受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="87bed-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="87bed-108">入出力名前空間の名前を格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="87bed-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87bed-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="87bed-109">Return Value</span></span>  
 <span data-ttu-id="87bed-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="87bed-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87bed-111">要件</span><span class="sxs-lookup"><span data-stu-id="87bed-111">Requirements</span></span>  
 <span data-ttu-id="87bed-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="87bed-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87bed-113">参照</span><span class="sxs-lookup"><span data-stu-id="87bed-113">See also</span></span>

- [<span data-ttu-id="87bed-114">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87bed-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
