---
title: ISymUnmanagedBinder2::GetReaderForFile2 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db917820de92b2e347385afc5217c0ca190825cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776833"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="9b924-102">ISymUnmanagedBinder2::GetReaderForFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="9b924-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="9b924-103">メタデータ インターフェイスおよびファイル名を指定されたを返します、正しい[ISymUnmanagedReader](isymunmanagedreader-interface.md)をモジュールに関連付けられているデバッグ シンボルを読み取る。</span><span class="sxs-lookup"><span data-stu-id="9b924-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="9b924-104">このメソッドより広範囲の検索よりもプログラム データベース (PDB) ファイル、 [isymunmanagedbinder::getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="9b924-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b924-105">構文</span><span class="sxs-lookup"><span data-stu-id="9b924-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b924-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b924-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="9b924-107">[in]メタデータ インポート インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9b924-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="9b924-108">[in]ファイル名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9b924-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="9b924-109">[in]検索パスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9b924-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="9b924-110">[in]値、 [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)シンボル リーダーの検索を行うときに使用されるポリシーを指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="9b924-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9b924-111">[out]設定されているポインターに返された[ISymUnmanagedReader](isymunmanagedreader-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9b924-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b924-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="9b924-112">Return Value</span></span>  
 <span data-ttu-id="9b924-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="9b924-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b924-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="9b924-114">Requirements</span></span>  
 <span data-ttu-id="9b924-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9b924-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b924-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b924-116">Remarks</span></span>  
 <span data-ttu-id="9b924-117">このバージョンのメソッドは、モジュール以外の領域の PDB ファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="9b924-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="9b924-118">サーチのポリシーを結合することで制御できる[CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b924-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="9b924-119">たとえば、`AllowReferencePathAccess | AllowSymbolServerAccess`実行可能ファイルの横にあると、シンボル サーバーの PDB の検索はレジストリの照会やのみが実行可能ファイルのパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b924-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="9b924-120">場合、`searchPath`パラメーターが指定されて、それらのディレクトリが常に検索されます。</span><span class="sxs-lookup"><span data-stu-id="9b924-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b924-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b924-121">See also</span></span>

- [<span data-ttu-id="9b924-122">ISymUnmanagedBinder2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b924-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="9b924-123">GetReaderForFile メソッド</span><span class="sxs-lookup"><span data-stu-id="9b924-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
