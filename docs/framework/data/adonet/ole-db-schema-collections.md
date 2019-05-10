---
title: OLE DB スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6c3441e86d4c5267418cf8002ba17d539c464d5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645896"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="06388-102">OLE DB スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="06388-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="06388-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 OLE DB プロバイダーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="06388-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="06388-104">Microsoft SQL Server OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="06388-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="06388-105">Microsoft SQL Server OLE DB Driver は、共通のスキーマ コレクションに加えて次の特定のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="06388-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="06388-106">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="06388-106">Tables</span></span>  
  
- <span data-ttu-id="06388-107">列</span><span class="sxs-lookup"><span data-stu-id="06388-107">Columns</span></span>  
  
- <span data-ttu-id="06388-108">手順</span><span class="sxs-lookup"><span data-stu-id="06388-108">Procedures</span></span>  
  
- <span data-ttu-id="06388-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="06388-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="06388-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="06388-110">Catalog</span></span>  
  
- <span data-ttu-id="06388-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="06388-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="06388-112">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="06388-112">Tables</span></span>  
  
|<span data-ttu-id="06388-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-113">ColumnName</span></span>|<span data-ttu-id="06388-114">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-115">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-116">String</span><span class="sxs-lookup"><span data-stu-id="06388-116">String</span></span>|  
|<span data-ttu-id="06388-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-118">String</span><span class="sxs-lookup"><span data-stu-id="06388-118">String</span></span>|  
|<span data-ttu-id="06388-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-119">TABLE_NAME</span></span>|<span data-ttu-id="06388-120">String</span><span class="sxs-lookup"><span data-stu-id="06388-120">String</span></span>|  
|<span data-ttu-id="06388-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-121">TABLE_TYPE</span></span>|<span data-ttu-id="06388-122">String</span><span class="sxs-lookup"><span data-stu-id="06388-122">String</span></span>|  
|<span data-ttu-id="06388-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-123">TABLE_GUID</span></span>|<span data-ttu-id="06388-124">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-124">Guid</span></span>|  
|<span data-ttu-id="06388-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-125">DESCRIPTION</span></span>|<span data-ttu-id="06388-126">String</span><span class="sxs-lookup"><span data-stu-id="06388-126">String</span></span>|  
|<span data-ttu-id="06388-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-127">TABLE_PROPID</span></span>|<span data-ttu-id="06388-128">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-128">Int64</span></span>|  
|<span data-ttu-id="06388-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="06388-129">DATE_CREATED</span></span>|<span data-ttu-id="06388-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-130">DateTime</span></span>|  
|<span data-ttu-id="06388-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="06388-131">DATE_MODIFIED</span></span>|<span data-ttu-id="06388-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="06388-133">列</span><span class="sxs-lookup"><span data-stu-id="06388-133">Columns</span></span>  
  
|<span data-ttu-id="06388-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-134">ColumnName</span></span>|<span data-ttu-id="06388-135">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-136">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-137">String</span><span class="sxs-lookup"><span data-stu-id="06388-137">String</span></span>|  
|<span data-ttu-id="06388-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-139">String</span><span class="sxs-lookup"><span data-stu-id="06388-139">String</span></span>|  
|<span data-ttu-id="06388-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-140">TABLE_NAME</span></span>|<span data-ttu-id="06388-141">String</span><span class="sxs-lookup"><span data-stu-id="06388-141">String</span></span>|  
|<span data-ttu-id="06388-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-142">COLUMN_NAME</span></span>|<span data-ttu-id="06388-143">String</span><span class="sxs-lookup"><span data-stu-id="06388-143">String</span></span>|  
|<span data-ttu-id="06388-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-144">COLUMN_GUID</span></span>|<span data-ttu-id="06388-145">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-145">Guid</span></span>|  
|<span data-ttu-id="06388-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-146">COLUMN_PROPID</span></span>|<span data-ttu-id="06388-147">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-147">Int64</span></span>|  
|<span data-ttu-id="06388-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="06388-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="06388-149">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-149">Int64</span></span>|  
|<span data-ttu-id="06388-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="06388-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="06388-151">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-151">Boolean</span></span>|  
|<span data-ttu-id="06388-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="06388-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="06388-153">String</span><span class="sxs-lookup"><span data-stu-id="06388-153">String</span></span>|  
|<span data-ttu-id="06388-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="06388-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="06388-155">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-155">Int64</span></span>|  
|<span data-ttu-id="06388-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="06388-156">IS_NULLABLE</span></span>|<span data-ttu-id="06388-157">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-157">Boolean</span></span>|  
|<span data-ttu-id="06388-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-158">DATA_TYPE</span></span>|<span data-ttu-id="06388-159">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-159">Int32</span></span>|  
|<span data-ttu-id="06388-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-160">TYPE_GUID</span></span>|<span data-ttu-id="06388-161">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-161">Guid</span></span>|  
|<span data-ttu-id="06388-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="06388-163">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-163">Int64</span></span>|  
|<span data-ttu-id="06388-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="06388-165">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-165">Int64</span></span>|  
|<span data-ttu-id="06388-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="06388-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="06388-167">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-167">Int32</span></span>|  
|<span data-ttu-id="06388-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="06388-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="06388-169">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-169">Int16</span></span>|  
|<span data-ttu-id="06388-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="06388-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="06388-171">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-171">Int64</span></span>|  
|<span data-ttu-id="06388-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="06388-173">String</span><span class="sxs-lookup"><span data-stu-id="06388-173">String</span></span>|  
|<span data-ttu-id="06388-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="06388-175">String</span><span class="sxs-lookup"><span data-stu-id="06388-175">String</span></span>|  
|<span data-ttu-id="06388-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="06388-177">String</span><span class="sxs-lookup"><span data-stu-id="06388-177">String</span></span>|  
|<span data-ttu-id="06388-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="06388-179">String</span><span class="sxs-lookup"><span data-stu-id="06388-179">String</span></span>|  
|<span data-ttu-id="06388-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="06388-181">String</span><span class="sxs-lookup"><span data-stu-id="06388-181">String</span></span>|  
|<span data-ttu-id="06388-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-182">COLLATION_NAME</span></span>|<span data-ttu-id="06388-183">String</span><span class="sxs-lookup"><span data-stu-id="06388-183">String</span></span>|  
|<span data-ttu-id="06388-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="06388-185">String</span><span class="sxs-lookup"><span data-stu-id="06388-185">String</span></span>|  
|<span data-ttu-id="06388-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="06388-187">String</span><span class="sxs-lookup"><span data-stu-id="06388-187">String</span></span>|  
|<span data-ttu-id="06388-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-188">DOMAIN_NAME</span></span>|<span data-ttu-id="06388-189">String</span><span class="sxs-lookup"><span data-stu-id="06388-189">String</span></span>|  
|<span data-ttu-id="06388-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-190">DESCRIPTION</span></span>|<span data-ttu-id="06388-191">String</span><span class="sxs-lookup"><span data-stu-id="06388-191">String</span></span>|  
|<span data-ttu-id="06388-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="06388-192">COLUMN_LCID</span></span>|<span data-ttu-id="06388-193">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-193">Int32</span></span>|  
|<span data-ttu-id="06388-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="06388-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="06388-195">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-195">Int32</span></span>|  
|<span data-ttu-id="06388-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="06388-196">COLUMN_SORTID</span></span>|<span data-ttu-id="06388-197">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-197">Int32</span></span>|  
|<span data-ttu-id="06388-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="06388-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="06388-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="06388-199">Byte[]</span></span>|  
|<span data-ttu-id="06388-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="06388-200">IS_COMPUTED</span></span>|<span data-ttu-id="06388-201">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="06388-202">手順</span><span class="sxs-lookup"><span data-stu-id="06388-202">Procedures</span></span>  
  
|<span data-ttu-id="06388-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-203">ColumnName</span></span>|<span data-ttu-id="06388-204">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="06388-206">String</span><span class="sxs-lookup"><span data-stu-id="06388-206">String</span></span>|  
|<span data-ttu-id="06388-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="06388-208">String</span><span class="sxs-lookup"><span data-stu-id="06388-208">String</span></span>|  
|<span data-ttu-id="06388-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="06388-210">String</span><span class="sxs-lookup"><span data-stu-id="06388-210">String</span></span>|  
|<span data-ttu-id="06388-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="06388-212">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-212">Int16</span></span>|  
|<span data-ttu-id="06388-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="06388-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="06388-214">String</span><span class="sxs-lookup"><span data-stu-id="06388-214">String</span></span>|  
|<span data-ttu-id="06388-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-215">DESCRIPTION</span></span>|<span data-ttu-id="06388-216">String</span><span class="sxs-lookup"><span data-stu-id="06388-216">String</span></span>|  
|<span data-ttu-id="06388-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="06388-217">DATE_CREATED</span></span>|<span data-ttu-id="06388-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-218">DateTime</span></span>|  
|<span data-ttu-id="06388-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="06388-219">DATE_MODIFIED</span></span>|<span data-ttu-id="06388-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="06388-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="06388-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="06388-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-222">ColumnName</span></span>|<span data-ttu-id="06388-223">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="06388-225">String</span><span class="sxs-lookup"><span data-stu-id="06388-225">String</span></span>|  
|<span data-ttu-id="06388-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="06388-227">String</span><span class="sxs-lookup"><span data-stu-id="06388-227">String</span></span>|  
|<span data-ttu-id="06388-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="06388-229">String</span><span class="sxs-lookup"><span data-stu-id="06388-229">String</span></span>|  
|<span data-ttu-id="06388-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-230">PARAMETER_NAME</span></span>|<span data-ttu-id="06388-231">String</span><span class="sxs-lookup"><span data-stu-id="06388-231">String</span></span>|  
|<span data-ttu-id="06388-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="06388-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="06388-233">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-233">Int32</span></span>|  
|<span data-ttu-id="06388-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="06388-235">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-235">Int32</span></span>|  
|<span data-ttu-id="06388-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="06388-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="06388-237">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-237">Boolean</span></span>|  
|<span data-ttu-id="06388-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="06388-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="06388-239">String</span><span class="sxs-lookup"><span data-stu-id="06388-239">String</span></span>|  
|<span data-ttu-id="06388-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="06388-240">IS_NULLABLE</span></span>|<span data-ttu-id="06388-241">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-241">Boolean</span></span>|  
|<span data-ttu-id="06388-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-242">DATA_TYPE</span></span>|<span data-ttu-id="06388-243">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-243">Int32</span></span>|  
|<span data-ttu-id="06388-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="06388-245">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-245">Int64</span></span>|  
|<span data-ttu-id="06388-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="06388-247">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-247">Int64</span></span>|  
|<span data-ttu-id="06388-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="06388-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="06388-249">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-249">Int32</span></span>|  
|<span data-ttu-id="06388-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="06388-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="06388-251">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-251">Int16</span></span>|  
|<span data-ttu-id="06388-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-252">DESCRIPTION</span></span>|<span data-ttu-id="06388-253">String</span><span class="sxs-lookup"><span data-stu-id="06388-253">String</span></span>|  
|<span data-ttu-id="06388-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-254">TYPE_NAME</span></span>|<span data-ttu-id="06388-255">String</span><span class="sxs-lookup"><span data-stu-id="06388-255">String</span></span>|  
|<span data-ttu-id="06388-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="06388-257">String</span><span class="sxs-lookup"><span data-stu-id="06388-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="06388-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="06388-258">Catalog</span></span>  
  
|<span data-ttu-id="06388-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-259">ColumnName</span></span>|<span data-ttu-id="06388-260">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-261">CATALOG_NAME</span></span>|<span data-ttu-id="06388-262">String</span><span class="sxs-lookup"><span data-stu-id="06388-262">String</span></span>|  
|<span data-ttu-id="06388-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-263">DESCRIPTION</span></span>|<span data-ttu-id="06388-264">String</span><span class="sxs-lookup"><span data-stu-id="06388-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="06388-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="06388-265">Indexes</span></span>  
  
|<span data-ttu-id="06388-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-266">ColumnName</span></span>|<span data-ttu-id="06388-267">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-268">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-269">String</span><span class="sxs-lookup"><span data-stu-id="06388-269">String</span></span>|  
|<span data-ttu-id="06388-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-271">String</span><span class="sxs-lookup"><span data-stu-id="06388-271">String</span></span>|  
|<span data-ttu-id="06388-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-272">TABLE_NAME</span></span>|<span data-ttu-id="06388-273">String</span><span class="sxs-lookup"><span data-stu-id="06388-273">String</span></span>|  
|<span data-ttu-id="06388-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-274">INDEX_CATALOG</span></span>|<span data-ttu-id="06388-275">String</span><span class="sxs-lookup"><span data-stu-id="06388-275">String</span></span>|  
|<span data-ttu-id="06388-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="06388-277">String</span><span class="sxs-lookup"><span data-stu-id="06388-277">String</span></span>|  
|<span data-ttu-id="06388-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-278">INDEX_NAME</span></span>|<span data-ttu-id="06388-279">String</span><span class="sxs-lookup"><span data-stu-id="06388-279">String</span></span>|  
|<span data-ttu-id="06388-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="06388-280">PRIMARY_KEY</span></span>|<span data-ttu-id="06388-281">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-281">Boolean</span></span>|  
|<span data-ttu-id="06388-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="06388-282">UNIQUE</span></span>|<span data-ttu-id="06388-283">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-283">Boolean</span></span>|  
|<span data-ttu-id="06388-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="06388-284">CLUSTERED</span></span>|<span data-ttu-id="06388-285">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-285">Boolean</span></span>|  
|<span data-ttu-id="06388-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-286">TYPE</span></span>|<span data-ttu-id="06388-287">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-287">Int32</span></span>|  
|<span data-ttu-id="06388-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="06388-288">FILL_FACTOR</span></span>|<span data-ttu-id="06388-289">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-289">Int32</span></span>|  
|<span data-ttu-id="06388-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="06388-290">INITIAL_SIZE</span></span>|<span data-ttu-id="06388-291">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-291">Int32</span></span>|  
|<span data-ttu-id="06388-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="06388-292">NULLS</span></span>|<span data-ttu-id="06388-293">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-293">Int32</span></span>|  
|<span data-ttu-id="06388-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="06388-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="06388-295">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-295">Boolean</span></span>|  
|<span data-ttu-id="06388-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="06388-296">AUTO_UPDATE</span></span>|<span data-ttu-id="06388-297">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-297">Boolean</span></span>|  
|<span data-ttu-id="06388-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="06388-298">NULL_COLLATION</span></span>|<span data-ttu-id="06388-299">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-299">Int32</span></span>|  
|<span data-ttu-id="06388-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="06388-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="06388-301">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-301">Int64</span></span>|  
|<span data-ttu-id="06388-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-302">COLUMN_NAME</span></span>|<span data-ttu-id="06388-303">String</span><span class="sxs-lookup"><span data-stu-id="06388-303">String</span></span>|  
|<span data-ttu-id="06388-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-304">COLUMN_GUID</span></span>|<span data-ttu-id="06388-305">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-305">Guid</span></span>|  
|<span data-ttu-id="06388-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-306">COLUMN_PROPID</span></span>|<span data-ttu-id="06388-307">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-307">Int64</span></span>|  
|<span data-ttu-id="06388-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="06388-308">COLLATION</span></span>|<span data-ttu-id="06388-309">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-309">Int16</span></span>|  
|<span data-ttu-id="06388-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="06388-310">CARDINALITY</span></span>|<span data-ttu-id="06388-311">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="06388-311">Decimal</span></span>|  
|<span data-ttu-id="06388-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="06388-312">PAGES</span></span>|<span data-ttu-id="06388-313">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-313">Int32</span></span>|  
|<span data-ttu-id="06388-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="06388-314">FILTER_CONDITION</span></span>|<span data-ttu-id="06388-315">String</span><span class="sxs-lookup"><span data-stu-id="06388-315">String</span></span>|  
|<span data-ttu-id="06388-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="06388-316">INTEGRATED</span></span>|<span data-ttu-id="06388-317">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="06388-318">Microsoft Oracle OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="06388-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="06388-319">Microsoft Oracle OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="06388-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="06388-320">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="06388-320">Tables</span></span>  
  
- <span data-ttu-id="06388-321">列</span><span class="sxs-lookup"><span data-stu-id="06388-321">Columns</span></span>  
  
- <span data-ttu-id="06388-322">手順</span><span class="sxs-lookup"><span data-stu-id="06388-322">Procedures</span></span>  
  
- <span data-ttu-id="06388-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="06388-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="06388-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="06388-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="06388-325">Views</span><span class="sxs-lookup"><span data-stu-id="06388-325">Views</span></span>  
  
- <span data-ttu-id="06388-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="06388-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="06388-327">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="06388-327">Tables</span></span>  
  
|<span data-ttu-id="06388-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-328">ColumnName</span></span>|<span data-ttu-id="06388-329">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-330">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-331">String</span><span class="sxs-lookup"><span data-stu-id="06388-331">String</span></span>|  
|<span data-ttu-id="06388-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-333">String</span><span class="sxs-lookup"><span data-stu-id="06388-333">String</span></span>|  
|<span data-ttu-id="06388-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-334">TABLE_NAME</span></span>|<span data-ttu-id="06388-335">String</span><span class="sxs-lookup"><span data-stu-id="06388-335">String</span></span>|  
|<span data-ttu-id="06388-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-336">TABLE_TYPE</span></span>|<span data-ttu-id="06388-337">String</span><span class="sxs-lookup"><span data-stu-id="06388-337">String</span></span>|  
|<span data-ttu-id="06388-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-338">TABLE_GUID</span></span>|<span data-ttu-id="06388-339">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-339">Guid</span></span>|  
|<span data-ttu-id="06388-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-340">DESCRIPTION</span></span>|<span data-ttu-id="06388-341">String</span><span class="sxs-lookup"><span data-stu-id="06388-341">String</span></span>|  
|<span data-ttu-id="06388-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-342">TABLE_PROPID</span></span>|<span data-ttu-id="06388-343">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-343">Int64</span></span>|  
|<span data-ttu-id="06388-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="06388-344">DATE_CREATED</span></span>|<span data-ttu-id="06388-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-345">DateTime</span></span>|  
|<span data-ttu-id="06388-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="06388-346">DATE_MODIFIED</span></span>|<span data-ttu-id="06388-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="06388-348">列</span><span class="sxs-lookup"><span data-stu-id="06388-348">Columns</span></span>  
  
|<span data-ttu-id="06388-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-349">ColumnName</span></span>|<span data-ttu-id="06388-350">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-351">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-352">String</span><span class="sxs-lookup"><span data-stu-id="06388-352">String</span></span>|  
|<span data-ttu-id="06388-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-354">String</span><span class="sxs-lookup"><span data-stu-id="06388-354">String</span></span>|  
|<span data-ttu-id="06388-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-355">TABLE_NAME</span></span>|<span data-ttu-id="06388-356">String</span><span class="sxs-lookup"><span data-stu-id="06388-356">String</span></span>|  
|<span data-ttu-id="06388-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-357">COLUMN_NAME</span></span>|<span data-ttu-id="06388-358">String</span><span class="sxs-lookup"><span data-stu-id="06388-358">String</span></span>|  
|<span data-ttu-id="06388-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-359">COLUMN_GUID</span></span>|<span data-ttu-id="06388-360">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-360">Guid</span></span>|  
|<span data-ttu-id="06388-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-361">COLUMN_PROPID</span></span>|<span data-ttu-id="06388-362">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-362">Int64</span></span>|  
|<span data-ttu-id="06388-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="06388-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="06388-364">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-364">Int64</span></span>|  
|<span data-ttu-id="06388-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="06388-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="06388-366">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-366">Boolean</span></span>|  
|<span data-ttu-id="06388-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="06388-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="06388-368">String</span><span class="sxs-lookup"><span data-stu-id="06388-368">String</span></span>|  
|<span data-ttu-id="06388-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="06388-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="06388-370">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-370">Int64</span></span>|  
|<span data-ttu-id="06388-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="06388-371">IS_NULLABLE</span></span>|<span data-ttu-id="06388-372">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-372">Boolean</span></span>|  
|<span data-ttu-id="06388-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-373">DATA_TYPE</span></span>|<span data-ttu-id="06388-374">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-374">Int32</span></span>|  
|<span data-ttu-id="06388-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-375">TYPE_GUID</span></span>|<span data-ttu-id="06388-376">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-376">Guid</span></span>|  
|<span data-ttu-id="06388-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="06388-378">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-378">Int64</span></span>|  
|<span data-ttu-id="06388-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="06388-380">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-380">Int64</span></span>|  
|<span data-ttu-id="06388-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="06388-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="06388-382">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-382">Int32</span></span>|  
|<span data-ttu-id="06388-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="06388-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="06388-384">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-384">Int16</span></span>|  
|<span data-ttu-id="06388-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="06388-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="06388-386">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-386">Int64</span></span>|  
|<span data-ttu-id="06388-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="06388-388">String</span><span class="sxs-lookup"><span data-stu-id="06388-388">String</span></span>|  
|<span data-ttu-id="06388-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="06388-390">String</span><span class="sxs-lookup"><span data-stu-id="06388-390">String</span></span>|  
|<span data-ttu-id="06388-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="06388-392">String</span><span class="sxs-lookup"><span data-stu-id="06388-392">String</span></span>|  
|<span data-ttu-id="06388-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="06388-394">String</span><span class="sxs-lookup"><span data-stu-id="06388-394">String</span></span>|  
|<span data-ttu-id="06388-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="06388-396">String</span><span class="sxs-lookup"><span data-stu-id="06388-396">String</span></span>|  
|<span data-ttu-id="06388-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-397">COLLATION_NAME</span></span>|<span data-ttu-id="06388-398">String</span><span class="sxs-lookup"><span data-stu-id="06388-398">String</span></span>|  
|<span data-ttu-id="06388-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="06388-400">String</span><span class="sxs-lookup"><span data-stu-id="06388-400">String</span></span>|  
|<span data-ttu-id="06388-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="06388-402">String</span><span class="sxs-lookup"><span data-stu-id="06388-402">String</span></span>|  
|<span data-ttu-id="06388-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-403">DOMAIN_NAME</span></span>|<span data-ttu-id="06388-404">String</span><span class="sxs-lookup"><span data-stu-id="06388-404">String</span></span>|  
|<span data-ttu-id="06388-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-405">DESCRIPTION</span></span>|<span data-ttu-id="06388-406">String</span><span class="sxs-lookup"><span data-stu-id="06388-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="06388-407">手順</span><span class="sxs-lookup"><span data-stu-id="06388-407">Procedures</span></span>  
  
|<span data-ttu-id="06388-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-408">ColumnName</span></span>|<span data-ttu-id="06388-409">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="06388-411">String</span><span class="sxs-lookup"><span data-stu-id="06388-411">String</span></span>|  
|<span data-ttu-id="06388-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="06388-413">String</span><span class="sxs-lookup"><span data-stu-id="06388-413">String</span></span>|  
|<span data-ttu-id="06388-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="06388-415">String</span><span class="sxs-lookup"><span data-stu-id="06388-415">String</span></span>|  
|<span data-ttu-id="06388-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="06388-417">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-417">Int16</span></span>|  
|<span data-ttu-id="06388-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="06388-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="06388-419">String</span><span class="sxs-lookup"><span data-stu-id="06388-419">String</span></span>|  
|<span data-ttu-id="06388-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-420">DESCRIPTION</span></span>|<span data-ttu-id="06388-421">String</span><span class="sxs-lookup"><span data-stu-id="06388-421">String</span></span>|  
|<span data-ttu-id="06388-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="06388-422">DATE_CREATED</span></span>|<span data-ttu-id="06388-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-423">DateTime</span></span>|  
|<span data-ttu-id="06388-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="06388-424">DATE_MODIFIED</span></span>|<span data-ttu-id="06388-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="06388-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="06388-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="06388-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-427">ColumnName</span></span>|<span data-ttu-id="06388-428">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="06388-430">String</span><span class="sxs-lookup"><span data-stu-id="06388-430">String</span></span>|  
|<span data-ttu-id="06388-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="06388-432">String</span><span class="sxs-lookup"><span data-stu-id="06388-432">String</span></span>|  
|<span data-ttu-id="06388-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="06388-434">String</span><span class="sxs-lookup"><span data-stu-id="06388-434">String</span></span>|  
|<span data-ttu-id="06388-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-435">COLUMN_NAME</span></span>|<span data-ttu-id="06388-436">String</span><span class="sxs-lookup"><span data-stu-id="06388-436">String</span></span>|  
|<span data-ttu-id="06388-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-437">COLUMN_GUID</span></span>|<span data-ttu-id="06388-438">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-438">Guid</span></span>|  
|<span data-ttu-id="06388-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-439">COLUMN_PROPID</span></span>|<span data-ttu-id="06388-440">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-440">Int64</span></span>|  
|<span data-ttu-id="06388-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="06388-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="06388-442">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-442">Int64</span></span>|  
|<span data-ttu-id="06388-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="06388-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="06388-444">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-444">Int64</span></span>|  
|<span data-ttu-id="06388-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="06388-445">IS_NULLABLE</span></span>|<span data-ttu-id="06388-446">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-446">Boolean</span></span>|  
|<span data-ttu-id="06388-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-447">DATA_TYPE</span></span>|<span data-ttu-id="06388-448">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-448">Int32</span></span>|  
|<span data-ttu-id="06388-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-449">TYPE_GUID</span></span>|<span data-ttu-id="06388-450">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-450">Guid</span></span>|  
|<span data-ttu-id="06388-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="06388-452">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-452">Int64</span></span>|  
|<span data-ttu-id="06388-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="06388-454">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-454">Int64</span></span>|  
|<span data-ttu-id="06388-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="06388-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="06388-456">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-456">Int32</span></span>|  
|<span data-ttu-id="06388-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="06388-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="06388-458">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-458">Int16</span></span>|  
|<span data-ttu-id="06388-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-459">DESCRIPTION</span></span>|<span data-ttu-id="06388-460">String</span><span class="sxs-lookup"><span data-stu-id="06388-460">String</span></span>|  
|<span data-ttu-id="06388-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="06388-461">OVERLOAD</span></span>|<span data-ttu-id="06388-462">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="06388-463">Views</span><span class="sxs-lookup"><span data-stu-id="06388-463">Views</span></span>  
  
|<span data-ttu-id="06388-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-464">ColumnName</span></span>|<span data-ttu-id="06388-465">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-466">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-467">String</span><span class="sxs-lookup"><span data-stu-id="06388-467">String</span></span>|  
|<span data-ttu-id="06388-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-469">String</span><span class="sxs-lookup"><span data-stu-id="06388-469">String</span></span>|  
|<span data-ttu-id="06388-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-470">TABLE_NAME</span></span>|<span data-ttu-id="06388-471">String</span><span class="sxs-lookup"><span data-stu-id="06388-471">String</span></span>|  
|<span data-ttu-id="06388-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="06388-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="06388-473">String</span><span class="sxs-lookup"><span data-stu-id="06388-473">String</span></span>|  
|<span data-ttu-id="06388-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="06388-474">CHECK_OPTION</span></span>|<span data-ttu-id="06388-475">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-475">Boolean</span></span>|  
|<span data-ttu-id="06388-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="06388-476">IS_UPDATABLE</span></span>|<span data-ttu-id="06388-477">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-477">Boolean</span></span>|  
|<span data-ttu-id="06388-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-478">DESCRIPTION</span></span>|<span data-ttu-id="06388-479">String</span><span class="sxs-lookup"><span data-stu-id="06388-479">String</span></span>|  
|<span data-ttu-id="06388-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="06388-480">DATE_CREATED</span></span>|<span data-ttu-id="06388-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-481">DateTime</span></span>|  
|<span data-ttu-id="06388-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="06388-482">DATE_MODIFIED</span></span>|<span data-ttu-id="06388-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="06388-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="06388-484">Indexes</span></span>  
  
|<span data-ttu-id="06388-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-485">ColumnName</span></span>|<span data-ttu-id="06388-486">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-487">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-488">String</span><span class="sxs-lookup"><span data-stu-id="06388-488">String</span></span>|  
|<span data-ttu-id="06388-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-490">String</span><span class="sxs-lookup"><span data-stu-id="06388-490">String</span></span>|  
|<span data-ttu-id="06388-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-491">TABLE_NAME</span></span>|<span data-ttu-id="06388-492">String</span><span class="sxs-lookup"><span data-stu-id="06388-492">String</span></span>|  
|<span data-ttu-id="06388-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-493">INDEX_CATALOG</span></span>|<span data-ttu-id="06388-494">String</span><span class="sxs-lookup"><span data-stu-id="06388-494">String</span></span>|  
|<span data-ttu-id="06388-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="06388-496">String</span><span class="sxs-lookup"><span data-stu-id="06388-496">String</span></span>|  
|<span data-ttu-id="06388-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-497">INDEX_NAME</span></span>|<span data-ttu-id="06388-498">String</span><span class="sxs-lookup"><span data-stu-id="06388-498">String</span></span>|  
|<span data-ttu-id="06388-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="06388-499">PRIMARY_KEY</span></span>|<span data-ttu-id="06388-500">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-500">Boolean</span></span>|  
|<span data-ttu-id="06388-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="06388-501">UNIQUE</span></span>|<span data-ttu-id="06388-502">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-502">Boolean</span></span>|  
|<span data-ttu-id="06388-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="06388-503">CLUSTERED</span></span>|<span data-ttu-id="06388-504">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-504">Boolean</span></span>|  
|<span data-ttu-id="06388-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-505">TYPE</span></span>|<span data-ttu-id="06388-506">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-506">Int32</span></span>|  
|<span data-ttu-id="06388-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="06388-507">FILL_FACTOR</span></span>|<span data-ttu-id="06388-508">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-508">Int32</span></span>|  
|<span data-ttu-id="06388-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="06388-509">INITIAL_SIZE</span></span>|<span data-ttu-id="06388-510">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-510">Int32</span></span>|  
|<span data-ttu-id="06388-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="06388-511">NULLS</span></span>|<span data-ttu-id="06388-512">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-512">Int32</span></span>|  
|<span data-ttu-id="06388-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="06388-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="06388-514">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-514">Boolean</span></span>|  
|<span data-ttu-id="06388-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="06388-515">AUTO_UPDATE</span></span>|<span data-ttu-id="06388-516">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-516">Boolean</span></span>|  
|<span data-ttu-id="06388-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="06388-517">NULL_COLLATION</span></span>|<span data-ttu-id="06388-518">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-518">Int32</span></span>|  
|<span data-ttu-id="06388-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="06388-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="06388-520">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-520">Int64</span></span>|  
|<span data-ttu-id="06388-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-521">COLUMN_NAME</span></span>|<span data-ttu-id="06388-522">String</span><span class="sxs-lookup"><span data-stu-id="06388-522">String</span></span>|  
|<span data-ttu-id="06388-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-523">COLUMN_GUID</span></span>|<span data-ttu-id="06388-524">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-524">Guid</span></span>|  
|<span data-ttu-id="06388-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-525">COLUMN_PROPID</span></span>|<span data-ttu-id="06388-526">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-526">Int64</span></span>|  
|<span data-ttu-id="06388-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="06388-527">COLLATION</span></span>|<span data-ttu-id="06388-528">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-528">Int16</span></span>|  
|<span data-ttu-id="06388-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="06388-529">CARDINALITY</span></span>|<span data-ttu-id="06388-530">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="06388-530">Decimal</span></span>|  
|<span data-ttu-id="06388-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="06388-531">PAGES</span></span>|<span data-ttu-id="06388-532">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-532">Int32</span></span>|  
|<span data-ttu-id="06388-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="06388-533">FILTER_CONDITION</span></span>|<span data-ttu-id="06388-534">String</span><span class="sxs-lookup"><span data-stu-id="06388-534">String</span></span>|  
|<span data-ttu-id="06388-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="06388-535">INTEGRATED</span></span>|<span data-ttu-id="06388-536">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="06388-537">Microsoft Jet OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="06388-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="06388-538">Microsoft Jet OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="06388-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="06388-539">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="06388-539">Tables</span></span>  
  
- <span data-ttu-id="06388-540">列</span><span class="sxs-lookup"><span data-stu-id="06388-540">Columns</span></span>  
  
- <span data-ttu-id="06388-541">手順</span><span class="sxs-lookup"><span data-stu-id="06388-541">Procedures</span></span>  
  
- <span data-ttu-id="06388-542">Views</span><span class="sxs-lookup"><span data-stu-id="06388-542">Views</span></span>  
  
- <span data-ttu-id="06388-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="06388-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="06388-544">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="06388-544">Tables</span></span>  
  
|<span data-ttu-id="06388-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-545">ColumnName</span></span>|<span data-ttu-id="06388-546">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-547">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-548">String</span><span class="sxs-lookup"><span data-stu-id="06388-548">String</span></span>|  
|<span data-ttu-id="06388-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-550">String</span><span class="sxs-lookup"><span data-stu-id="06388-550">String</span></span>|  
|<span data-ttu-id="06388-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-551">TABLE_NAME</span></span>|<span data-ttu-id="06388-552">String</span><span class="sxs-lookup"><span data-stu-id="06388-552">String</span></span>|  
|<span data-ttu-id="06388-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-553">TABLE_TYPE</span></span>|<span data-ttu-id="06388-554">String</span><span class="sxs-lookup"><span data-stu-id="06388-554">String</span></span>|  
|<span data-ttu-id="06388-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-555">TABLE_GUID</span></span>|<span data-ttu-id="06388-556">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-556">Guid</span></span>|  
|<span data-ttu-id="06388-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-557">DESCRIPTION</span></span>|<span data-ttu-id="06388-558">String</span><span class="sxs-lookup"><span data-stu-id="06388-558">String</span></span>|  
|<span data-ttu-id="06388-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-559">TABLE_PROPID</span></span>|<span data-ttu-id="06388-560">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-560">Int64</span></span>|  
|<span data-ttu-id="06388-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="06388-561">DATE_CREATED</span></span>|<span data-ttu-id="06388-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-562">DateTime</span></span>|  
|<span data-ttu-id="06388-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="06388-563">DATE_MODIFIED</span></span>|<span data-ttu-id="06388-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="06388-565">列</span><span class="sxs-lookup"><span data-stu-id="06388-565">Columns</span></span>  
  
|<span data-ttu-id="06388-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-566">ColumnName</span></span>|<span data-ttu-id="06388-567">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-568">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-569">String</span><span class="sxs-lookup"><span data-stu-id="06388-569">String</span></span>|  
|<span data-ttu-id="06388-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-571">String</span><span class="sxs-lookup"><span data-stu-id="06388-571">String</span></span>|  
|<span data-ttu-id="06388-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-572">TABLE_NAME</span></span>|<span data-ttu-id="06388-573">String</span><span class="sxs-lookup"><span data-stu-id="06388-573">String</span></span>|  
|<span data-ttu-id="06388-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-574">COLUMN_NAME</span></span>|<span data-ttu-id="06388-575">String</span><span class="sxs-lookup"><span data-stu-id="06388-575">String</span></span>|  
|<span data-ttu-id="06388-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-576">COLUMN_GUID</span></span>|<span data-ttu-id="06388-577">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-577">Guid</span></span>|  
|<span data-ttu-id="06388-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-578">COLUMN_PROPID</span></span>|<span data-ttu-id="06388-579">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-579">Int64</span></span>|  
|<span data-ttu-id="06388-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="06388-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="06388-581">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-581">Int64</span></span>|  
|<span data-ttu-id="06388-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="06388-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="06388-583">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-583">Boolean</span></span>|  
|<span data-ttu-id="06388-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="06388-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="06388-585">String</span><span class="sxs-lookup"><span data-stu-id="06388-585">String</span></span>|  
|<span data-ttu-id="06388-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="06388-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="06388-587">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-587">Int64</span></span>|  
|<span data-ttu-id="06388-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="06388-588">IS_NULLABLE</span></span>|<span data-ttu-id="06388-589">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-589">Boolean</span></span>|  
|<span data-ttu-id="06388-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-590">DATA_TYPE</span></span>|<span data-ttu-id="06388-591">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-591">Int32</span></span>|  
|<span data-ttu-id="06388-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-592">TYPE_GUID</span></span>|<span data-ttu-id="06388-593">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-593">Guid</span></span>|  
|<span data-ttu-id="06388-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="06388-595">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-595">Int64</span></span>|  
|<span data-ttu-id="06388-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="06388-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="06388-597">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-597">Int64</span></span>|  
|<span data-ttu-id="06388-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="06388-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="06388-599">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-599">Int32</span></span>|  
|<span data-ttu-id="06388-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="06388-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="06388-601">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-601">Int16</span></span>|  
|<span data-ttu-id="06388-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="06388-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="06388-603">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-603">Int64</span></span>|  
|<span data-ttu-id="06388-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="06388-605">String</span><span class="sxs-lookup"><span data-stu-id="06388-605">String</span></span>|  
|<span data-ttu-id="06388-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="06388-607">String</span><span class="sxs-lookup"><span data-stu-id="06388-607">String</span></span>|  
|<span data-ttu-id="06388-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="06388-609">String</span><span class="sxs-lookup"><span data-stu-id="06388-609">String</span></span>|  
|<span data-ttu-id="06388-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="06388-611">String</span><span class="sxs-lookup"><span data-stu-id="06388-611">String</span></span>|  
|<span data-ttu-id="06388-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="06388-613">String</span><span class="sxs-lookup"><span data-stu-id="06388-613">String</span></span>|  
|<span data-ttu-id="06388-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-614">COLLATION_NAME</span></span>|<span data-ttu-id="06388-615">String</span><span class="sxs-lookup"><span data-stu-id="06388-615">String</span></span>|  
|<span data-ttu-id="06388-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="06388-617">String</span><span class="sxs-lookup"><span data-stu-id="06388-617">String</span></span>|  
|<span data-ttu-id="06388-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="06388-619">String</span><span class="sxs-lookup"><span data-stu-id="06388-619">String</span></span>|  
|<span data-ttu-id="06388-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-620">DOMAIN_NAME</span></span>|<span data-ttu-id="06388-621">String</span><span class="sxs-lookup"><span data-stu-id="06388-621">String</span></span>|  
|<span data-ttu-id="06388-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-622">DESCRIPTION</span></span>|<span data-ttu-id="06388-623">String</span><span class="sxs-lookup"><span data-stu-id="06388-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="06388-624">手順</span><span class="sxs-lookup"><span data-stu-id="06388-624">Procedures</span></span>  
  
|<span data-ttu-id="06388-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-625">ColumnName</span></span>|<span data-ttu-id="06388-626">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="06388-628">String</span><span class="sxs-lookup"><span data-stu-id="06388-628">String</span></span>|  
|<span data-ttu-id="06388-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="06388-630">String</span><span class="sxs-lookup"><span data-stu-id="06388-630">String</span></span>|  
|<span data-ttu-id="06388-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="06388-632">String</span><span class="sxs-lookup"><span data-stu-id="06388-632">String</span></span>|  
|<span data-ttu-id="06388-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="06388-634">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-634">Int16</span></span>|  
|<span data-ttu-id="06388-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="06388-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="06388-636">String</span><span class="sxs-lookup"><span data-stu-id="06388-636">String</span></span>|  
|<span data-ttu-id="06388-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-637">DESCRIPTION</span></span>|<span data-ttu-id="06388-638">String</span><span class="sxs-lookup"><span data-stu-id="06388-638">String</span></span>|  
|<span data-ttu-id="06388-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="06388-639">DATE_CREATED</span></span>|<span data-ttu-id="06388-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-640">DateTime</span></span>|  
|<span data-ttu-id="06388-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="06388-641">DATE_MODIFIED</span></span>|<span data-ttu-id="06388-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="06388-643">Views</span><span class="sxs-lookup"><span data-stu-id="06388-643">Views</span></span>  
  
|<span data-ttu-id="06388-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-644">ColumnName</span></span>|<span data-ttu-id="06388-645">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-646">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-647">String</span><span class="sxs-lookup"><span data-stu-id="06388-647">String</span></span>|  
|<span data-ttu-id="06388-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-649">String</span><span class="sxs-lookup"><span data-stu-id="06388-649">String</span></span>|  
|<span data-ttu-id="06388-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-650">TABLE_NAME</span></span>|<span data-ttu-id="06388-651">String</span><span class="sxs-lookup"><span data-stu-id="06388-651">String</span></span>|  
|<span data-ttu-id="06388-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="06388-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="06388-653">String</span><span class="sxs-lookup"><span data-stu-id="06388-653">String</span></span>|  
|<span data-ttu-id="06388-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="06388-654">CHECK_OPTION</span></span>|<span data-ttu-id="06388-655">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-655">Boolean</span></span>|  
|<span data-ttu-id="06388-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="06388-656">IS_UPDATABLE</span></span>|<span data-ttu-id="06388-657">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-657">Boolean</span></span>|  
|<span data-ttu-id="06388-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06388-658">DESCRIPTION</span></span>|<span data-ttu-id="06388-659">String</span><span class="sxs-lookup"><span data-stu-id="06388-659">String</span></span>|  
|<span data-ttu-id="06388-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="06388-660">DATE_CREATED</span></span>|<span data-ttu-id="06388-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-661">DateTime</span></span>|  
|<span data-ttu-id="06388-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="06388-662">DATE_MODIFIED</span></span>|<span data-ttu-id="06388-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="06388-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="06388-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="06388-664">Indexes</span></span>  
  
|<span data-ttu-id="06388-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="06388-665">ColumnName</span></span>|<span data-ttu-id="06388-666">DataType</span><span class="sxs-lookup"><span data-stu-id="06388-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="06388-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-667">TABLE_CATALOG</span></span>|<span data-ttu-id="06388-668">String</span><span class="sxs-lookup"><span data-stu-id="06388-668">String</span></span>|  
|<span data-ttu-id="06388-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="06388-670">String</span><span class="sxs-lookup"><span data-stu-id="06388-670">String</span></span>|  
|<span data-ttu-id="06388-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-671">TABLE_NAME</span></span>|<span data-ttu-id="06388-672">String</span><span class="sxs-lookup"><span data-stu-id="06388-672">String</span></span>|  
|<span data-ttu-id="06388-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="06388-673">INDEX_CATALOG</span></span>|<span data-ttu-id="06388-674">String</span><span class="sxs-lookup"><span data-stu-id="06388-674">String</span></span>|  
|<span data-ttu-id="06388-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="06388-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="06388-676">String</span><span class="sxs-lookup"><span data-stu-id="06388-676">String</span></span>|  
|<span data-ttu-id="06388-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-677">INDEX_NAME</span></span>|<span data-ttu-id="06388-678">String</span><span class="sxs-lookup"><span data-stu-id="06388-678">String</span></span>|  
|<span data-ttu-id="06388-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="06388-679">PRIMARY_KEY</span></span>|<span data-ttu-id="06388-680">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-680">Boolean</span></span>|  
|<span data-ttu-id="06388-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="06388-681">UNIQUE</span></span>|<span data-ttu-id="06388-682">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-682">Boolean</span></span>|  
|<span data-ttu-id="06388-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="06388-683">CLUSTERED</span></span>|<span data-ttu-id="06388-684">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-684">Boolean</span></span>|  
|<span data-ttu-id="06388-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="06388-685">TYPE</span></span>|<span data-ttu-id="06388-686">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-686">Int32</span></span>|  
|<span data-ttu-id="06388-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="06388-687">FILL_FACTOR</span></span>|<span data-ttu-id="06388-688">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-688">Int32</span></span>|  
|<span data-ttu-id="06388-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="06388-689">INITIAL_SIZE</span></span>|<span data-ttu-id="06388-690">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-690">Int32</span></span>|  
|<span data-ttu-id="06388-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="06388-691">NULLS</span></span>|<span data-ttu-id="06388-692">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-692">Int32</span></span>|  
|<span data-ttu-id="06388-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="06388-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="06388-694">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-694">Boolean</span></span>|  
|<span data-ttu-id="06388-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="06388-695">AUTO_UPDATE</span></span>|<span data-ttu-id="06388-696">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-696">Boolean</span></span>|  
|<span data-ttu-id="06388-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="06388-697">NULL_COLLATION</span></span>|<span data-ttu-id="06388-698">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-698">Int32</span></span>|  
|<span data-ttu-id="06388-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="06388-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="06388-700">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-700">Int64</span></span>|  
|<span data-ttu-id="06388-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="06388-701">COLUMN_NAME</span></span>|<span data-ttu-id="06388-702">String</span><span class="sxs-lookup"><span data-stu-id="06388-702">String</span></span>|  
|<span data-ttu-id="06388-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="06388-703">COLUMN_GUID</span></span>|<span data-ttu-id="06388-704">GUID</span><span class="sxs-lookup"><span data-stu-id="06388-704">Guid</span></span>|  
|<span data-ttu-id="06388-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="06388-705">COLUMN_PROPID</span></span>|<span data-ttu-id="06388-706">Int64</span><span class="sxs-lookup"><span data-stu-id="06388-706">Int64</span></span>|  
|<span data-ttu-id="06388-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="06388-707">COLLATION</span></span>|<span data-ttu-id="06388-708">Int16</span><span class="sxs-lookup"><span data-stu-id="06388-708">Int16</span></span>|  
|<span data-ttu-id="06388-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="06388-709">CARDINALITY</span></span>|<span data-ttu-id="06388-710">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="06388-710">Decimal</span></span>|  
|<span data-ttu-id="06388-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="06388-711">PAGES</span></span>|<span data-ttu-id="06388-712">Int32</span><span class="sxs-lookup"><span data-stu-id="06388-712">Int32</span></span>|  
|<span data-ttu-id="06388-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="06388-713">FILTER_CONDITION</span></span>|<span data-ttu-id="06388-714">String</span><span class="sxs-lookup"><span data-stu-id="06388-714">String</span></span>|  
|<span data-ttu-id="06388-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="06388-715">INTEGRATED</span></span>|<span data-ttu-id="06388-716">ブール型</span><span class="sxs-lookup"><span data-stu-id="06388-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06388-717">関連項目</span><span class="sxs-lookup"><span data-stu-id="06388-717">See also</span></span>

- [<span data-ttu-id="06388-718">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="06388-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
