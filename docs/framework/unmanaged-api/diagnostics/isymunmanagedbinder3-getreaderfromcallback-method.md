---
title: ISymUnmanagedBinder3::GetReaderFromCallback メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9487cf89d87b5f373302dc49a08c4fabb719e746
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160772"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="43088-102">ISymUnmanagedBinder3::GetReaderFromCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="43088-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="43088-103">実装またはコールバックを使用していずれかを指定できます、`IID_IDiaReadExeAtRVACallback`または`IID_IDiaReadExeAtOffsetCallback`をメモリからデバッグ ディレクトリ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="43088-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43088-104">構文</span><span class="sxs-lookup"><span data-stu-id="43088-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43088-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43088-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="43088-106">[in]メタデータ インポート インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="43088-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="43088-107">[in]ファイル名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="43088-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="43088-108">[in]検索パスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="43088-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="43088-109">[in]値、 [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)シンボル リーダーの検索を行うときに使用されるポリシーを指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="43088-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="43088-110">[in]コールバック関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="43088-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="43088-111">[out]設定されているポインターに返された[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="43088-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43088-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="43088-112">Return Value</span></span>  
 <span data-ttu-id="43088-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="43088-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43088-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="43088-114">Requirements</span></span>  
 <span data-ttu-id="43088-115">**ヘッダー:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="43088-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43088-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="43088-116">See also</span></span>

- [<span data-ttu-id="43088-117">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43088-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
