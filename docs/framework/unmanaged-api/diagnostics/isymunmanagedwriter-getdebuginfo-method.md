---
title: ISymUnmanagedWriter::GetDebugInfo メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 41d96c6d2024dbc3cab669f2dba2f99faef89f4b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074249"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="0db1c-102">ISymUnmanagedWriter::GetDebugInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="0db1c-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>
<span data-ttu-id="0db1c-103">コンパイラがポータブル実行可能 (PE) ファイル ヘッダーのデバッグ ディレクトリのエントリを書き込むために必要な情報を返します。</span><span class="sxs-lookup"><span data-stu-id="0db1c-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="0db1c-104">シンボル ライターを除くのすべてのフィールドは`TimeDateStamp`と`PointerToRawData`します。</span><span class="sxs-lookup"><span data-stu-id="0db1c-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="0db1c-105">(コンパイラは、これら 2 つのフィールドを適切に設定を行います)。</span><span class="sxs-lookup"><span data-stu-id="0db1c-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="0db1c-106">このメソッドを呼び出す、PE ファイルまでデータ blob の出力、設定する必要があります、コンパイラ、 `PointerToRawData` 、出力されたデータをポイントして、IMAGE_DEBUG_DIRECTORY を PE ファイルに書き込む IMAGE_DEBUG_DIRECTORY フィールド。</span><span class="sxs-lookup"><span data-stu-id="0db1c-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="0db1c-107">コンパイラを設定する必要がありますも、`TimeDateStamp`フィールドと等しい、 `TimeDateStamp` PE ファイルが生成されるのです。</span><span class="sxs-lookup"><span data-stu-id="0db1c-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0db1c-108">構文</span><span class="sxs-lookup"><span data-stu-id="0db1c-108">Syntax</span></span>  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0db1c-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0db1c-109">Parameters</span></span>  
 `pIDD`  
 <span data-ttu-id="0db1c-110">[入力、出力]シンボルのライターが入力する、IMAGE_DEBUG_DIRECTORY へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0db1c-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="0db1c-111">[in]A`DWORD`デバッグ データのサイズを格納しています。</span><span class="sxs-lookup"><span data-stu-id="0db1c-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="0db1c-112">[out]ポインターを`DWORD`デバッグ データの格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="0db1c-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="0db1c-113">[out]シンボル ストアのデバッグ データを保持するために十分な大きさであるバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0db1c-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0db1c-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="0db1c-114">Return Value</span></span>  
 <span data-ttu-id="0db1c-115">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="0db1c-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0db1c-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="0db1c-116">Requirements</span></span>  
 <span data-ttu-id="0db1c-117">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0db1c-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db1c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0db1c-118">See also</span></span>

- [<span data-ttu-id="0db1c-119">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0db1c-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
