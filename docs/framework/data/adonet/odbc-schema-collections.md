---
title: ODBC スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772048"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="d9b95-102">ODBC スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="d9b95-102">ODBC Schema Collections</span></span>

<span data-ttu-id="d9b95-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 ODBC ドライバーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d9b95-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="d9b95-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="d9b95-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="d9b95-105">Microsoft SQL Server ODBC Driver には、共通のスキーマ コレクションに加えて次の特定のスキーマ コレクションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d9b95-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="d9b95-106">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="d9b95-106">Tables</span></span>

- <span data-ttu-id="d9b95-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="d9b95-107">Indexes</span></span>

- <span data-ttu-id="d9b95-108">列</span><span class="sxs-lookup"><span data-stu-id="d9b95-108">Columns</span></span>

- <span data-ttu-id="d9b95-109">手順</span><span class="sxs-lookup"><span data-stu-id="d9b95-109">Procedures</span></span>

- <span data-ttu-id="d9b95-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d9b95-110">ProcedureColumns</span></span>

- <span data-ttu-id="d9b95-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d9b95-111">ProcedureParameters</span></span>

- <span data-ttu-id="d9b95-112">Views</span><span class="sxs-lookup"><span data-stu-id="d9b95-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="d9b95-113">Tables と Views</span><span class="sxs-lookup"><span data-stu-id="d9b95-113">Tables and Views</span></span>

|<span data-ttu-id="d9b95-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-114">ColumnName</span></span>|<span data-ttu-id="d9b95-115">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d9b95-116">TABLE_CAT</span></span>|<span data-ttu-id="d9b95-117">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-117">String</span></span>|
|<span data-ttu-id="d9b95-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d9b95-118">TABLE_SCHEM</span></span>|<span data-ttu-id="d9b95-119">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-119">String</span></span>|
|<span data-ttu-id="d9b95-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-120">TABLE_NAME</span></span>|<span data-ttu-id="d9b95-121">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-121">String</span></span>|
|<span data-ttu-id="d9b95-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-122">TABLE_TYPE</span></span>|<span data-ttu-id="d9b95-123">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-123">String</span></span>|
|<span data-ttu-id="d9b95-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-124">REMARKS</span></span>|<span data-ttu-id="d9b95-125">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="d9b95-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="d9b95-126">Indexes</span></span>

|<span data-ttu-id="d9b95-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-127">ColumnName</span></span>|<span data-ttu-id="d9b95-128">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d9b95-129">TABLE_CAT</span></span>|<span data-ttu-id="d9b95-130">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-130">String</span></span>|
|<span data-ttu-id="d9b95-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d9b95-131">TABLE_SCHEM</span></span>|<span data-ttu-id="d9b95-132">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-132">String</span></span>|
|<span data-ttu-id="d9b95-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-133">TABLE_NAME</span></span>|<span data-ttu-id="d9b95-134">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-134">String</span></span>|
|<span data-ttu-id="d9b95-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d9b95-135">NON_UNIQUE</span></span>|<span data-ttu-id="d9b95-136">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-136">Int16</span></span>|
|<span data-ttu-id="d9b95-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d9b95-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="d9b95-138">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-138">String</span></span>|
|<span data-ttu-id="d9b95-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-139">INDEX_NAME</span></span>|<span data-ttu-id="d9b95-140">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-140">String</span></span>|
|<span data-ttu-id="d9b95-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-141">TYPE</span></span>|<span data-ttu-id="d9b95-142">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-142">Int16</span></span>|
|<span data-ttu-id="d9b95-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="d9b95-144">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-144">Int16</span></span>|
|<span data-ttu-id="d9b95-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-145">COLUMN_NAME</span></span>|<span data-ttu-id="d9b95-146">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-146">String</span></span>|
|<span data-ttu-id="d9b95-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="d9b95-147">ASC_OR_DESC</span></span>|<span data-ttu-id="d9b95-148">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-148">String</span></span>|
|<span data-ttu-id="d9b95-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d9b95-149">CARDINALITY</span></span>|<span data-ttu-id="d9b95-150">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-150">Int32</span></span>|
|<span data-ttu-id="d9b95-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="d9b95-151">PAGES</span></span>|<span data-ttu-id="d9b95-152">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-152">Int32</span></span>|
|<span data-ttu-id="d9b95-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-153">FILTER_CONDITION</span></span>|<span data-ttu-id="d9b95-154">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-154">String</span></span>|
|<span data-ttu-id="d9b95-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d9b95-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d9b95-156">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-156">String</span></span>|
|<span data-ttu-id="d9b95-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="d9b95-158">Byte</span><span class="sxs-lookup"><span data-stu-id="d9b95-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="d9b95-159">列</span><span class="sxs-lookup"><span data-stu-id="d9b95-159">Columns</span></span>

|<span data-ttu-id="d9b95-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-160">ColumnName</span></span>|<span data-ttu-id="d9b95-161">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d9b95-162">TABLE_CAT</span></span>|<span data-ttu-id="d9b95-163">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-163">String</span></span>|
|<span data-ttu-id="d9b95-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d9b95-164">TABLE_SCHEM</span></span>|<span data-ttu-id="d9b95-165">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-165">String</span></span>|
|<span data-ttu-id="d9b95-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-166">TABLE_NAME</span></span>|<span data-ttu-id="d9b95-167">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-167">String</span></span>|
|<span data-ttu-id="d9b95-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-168">COLUMN_NAME</span></span>|<span data-ttu-id="d9b95-169">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-169">String</span></span>|
|<span data-ttu-id="d9b95-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-170">DATA_TYPE</span></span>|<span data-ttu-id="d9b95-171">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-171">Int16</span></span>|
|<span data-ttu-id="d9b95-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-172">TYPE_NAME</span></span>|<span data-ttu-id="d9b95-173">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-173">String</span></span>|
|<span data-ttu-id="d9b95-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d9b95-174">COLUMN_SIZE</span></span>|<span data-ttu-id="d9b95-175">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-175">Int32</span></span>|
|<span data-ttu-id="d9b95-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="d9b95-177">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-177">Int32</span></span>|
|<span data-ttu-id="d9b95-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d9b95-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d9b95-179">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-179">Int16</span></span>|
|<span data-ttu-id="d9b95-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d9b95-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d9b95-181">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-181">Int16</span></span>|
|<span data-ttu-id="d9b95-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-182">NULLABLE</span></span>|<span data-ttu-id="d9b95-183">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-183">Int16</span></span>|
|<span data-ttu-id="d9b95-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-184">REMARKS</span></span>|<span data-ttu-id="d9b95-185">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-185">String</span></span>|
|<span data-ttu-id="d9b95-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d9b95-186">COLUMN_DEF</span></span>|<span data-ttu-id="d9b95-187">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-187">String</span></span>|
|<span data-ttu-id="d9b95-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d9b95-189">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-189">Int16</span></span>|
|<span data-ttu-id="d9b95-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d9b95-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d9b95-191">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-191">Int16</span></span>|
|<span data-ttu-id="d9b95-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d9b95-193">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-193">Int32</span></span>|
|<span data-ttu-id="d9b95-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="d9b95-195">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-195">Int32</span></span>|
|<span data-ttu-id="d9b95-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-196">IS_NULLABLE</span></span>|<span data-ttu-id="d9b95-197">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-197">String</span></span>|
|<span data-ttu-id="d9b95-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d9b95-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d9b95-199">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-199">String</span></span>|
|<span data-ttu-id="d9b95-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d9b95-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d9b95-201">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-201">String</span></span>|
|<span data-ttu-id="d9b95-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="d9b95-203">Byte</span><span class="sxs-lookup"><span data-stu-id="d9b95-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="d9b95-204">手順</span><span class="sxs-lookup"><span data-stu-id="d9b95-204">Procedures</span></span>

|<span data-ttu-id="d9b95-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-205">ColumnName</span></span>|<span data-ttu-id="d9b95-206">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d9b95-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="d9b95-208">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-208">String</span></span>|
|<span data-ttu-id="d9b95-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d9b95-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d9b95-210">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-210">String</span></span>|
|<span data-ttu-id="d9b95-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="d9b95-212">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-212">String</span></span>|
|<span data-ttu-id="d9b95-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d9b95-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d9b95-214">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-214">Int32</span></span>|
|<span data-ttu-id="d9b95-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d9b95-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d9b95-216">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-216">Int32</span></span>|
|<span data-ttu-id="d9b95-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d9b95-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d9b95-218">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-218">Int32</span></span>|
|<span data-ttu-id="d9b95-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-219">REMARKS</span></span>|<span data-ttu-id="d9b95-220">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-220">String</span></span>|
|<span data-ttu-id="d9b95-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d9b95-222">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="d9b95-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d9b95-223">ProcedureColumns</span></span>

|<span data-ttu-id="d9b95-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-224">ColumnName</span></span>|<span data-ttu-id="d9b95-225">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d9b95-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="d9b95-227">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-227">String</span></span>|
|<span data-ttu-id="d9b95-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d9b95-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d9b95-229">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-229">String</span></span>|
|<span data-ttu-id="d9b95-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="d9b95-231">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-231">String</span></span>|
|<span data-ttu-id="d9b95-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-232">COLUMN_NAME</span></span>|<span data-ttu-id="d9b95-233">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-233">String</span></span>|
|<span data-ttu-id="d9b95-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-234">COLUMN_TYPE</span></span>|<span data-ttu-id="d9b95-235">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-235">Int16</span></span>|
|<span data-ttu-id="d9b95-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-236">DATA_TYPE</span></span>|<span data-ttu-id="d9b95-237">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-237">Int16</span></span>|
|<span data-ttu-id="d9b95-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-238">TYPE_NAME</span></span>|<span data-ttu-id="d9b95-239">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-239">String</span></span>|
|<span data-ttu-id="d9b95-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d9b95-240">COLUMN_SIZE</span></span>|<span data-ttu-id="d9b95-241">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-241">Int32</span></span>|
|<span data-ttu-id="d9b95-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="d9b95-243">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-243">Int32</span></span>|
|<span data-ttu-id="d9b95-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d9b95-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d9b95-245">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-245">Int16</span></span>|
|<span data-ttu-id="d9b95-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d9b95-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d9b95-247">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-247">Int16</span></span>|
|<span data-ttu-id="d9b95-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-248">NULLABLE</span></span>|<span data-ttu-id="d9b95-249">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-249">Int16</span></span>|
|<span data-ttu-id="d9b95-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-250">REMARKS</span></span>|<span data-ttu-id="d9b95-251">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-251">String</span></span>|
|<span data-ttu-id="d9b95-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d9b95-252">COLUMN_DEF</span></span>|<span data-ttu-id="d9b95-253">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-253">String</span></span>|
|<span data-ttu-id="d9b95-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d9b95-255">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-255">Int16</span></span>|
|<span data-ttu-id="d9b95-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d9b95-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d9b95-257">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-257">Int16</span></span>|
|<span data-ttu-id="d9b95-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d9b95-259">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-259">Int32</span></span>|
|<span data-ttu-id="d9b95-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="d9b95-261">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-261">Int32</span></span>|
|<span data-ttu-id="d9b95-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-262">IS_NULLABLE</span></span>|<span data-ttu-id="d9b95-263">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-263">String</span></span>|
|<span data-ttu-id="d9b95-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d9b95-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d9b95-265">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-265">String</span></span>|
|<span data-ttu-id="d9b95-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d9b95-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d9b95-267">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-267">String</span></span>|
|<span data-ttu-id="d9b95-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="d9b95-269">Byte</span><span class="sxs-lookup"><span data-stu-id="d9b95-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="d9b95-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d9b95-270">ProcedureParameters</span></span>

|<span data-ttu-id="d9b95-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-271">ColumnName</span></span>|<span data-ttu-id="d9b95-272">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d9b95-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="d9b95-274">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-274">String</span></span>|
|<span data-ttu-id="d9b95-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d9b95-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d9b95-276">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-276">String</span></span>|
|<span data-ttu-id="d9b95-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="d9b95-278">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-278">String</span></span>|
|<span data-ttu-id="d9b95-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-279">COLUMN_NAME</span></span>|<span data-ttu-id="d9b95-280">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-280">String</span></span>|
|<span data-ttu-id="d9b95-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-281">COLUMN_TYPE</span></span>|<span data-ttu-id="d9b95-282">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-282">Int16</span></span>|
|<span data-ttu-id="d9b95-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-283">DATA_TYPE</span></span>|<span data-ttu-id="d9b95-284">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-284">Int16</span></span>|
|<span data-ttu-id="d9b95-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-285">TYPE_NAME</span></span>|<span data-ttu-id="d9b95-286">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-286">String</span></span>|
|<span data-ttu-id="d9b95-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d9b95-287">COLUMN_SIZE</span></span>|<span data-ttu-id="d9b95-288">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-288">Int32</span></span>|
|<span data-ttu-id="d9b95-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="d9b95-290">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-290">Int32</span></span>|
|<span data-ttu-id="d9b95-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d9b95-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d9b95-292">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-292">Int16</span></span>|
|<span data-ttu-id="d9b95-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d9b95-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d9b95-294">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-294">Int16</span></span>|
|<span data-ttu-id="d9b95-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-295">NULLABLE</span></span>|<span data-ttu-id="d9b95-296">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-296">Int16</span></span>|
|<span data-ttu-id="d9b95-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-297">REMARKS</span></span>|<span data-ttu-id="d9b95-298">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-298">String</span></span>|
|<span data-ttu-id="d9b95-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d9b95-299">COLUMN_DEF</span></span>|<span data-ttu-id="d9b95-300">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-300">String</span></span>|
|<span data-ttu-id="d9b95-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d9b95-302">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-302">Int16</span></span>|
|<span data-ttu-id="d9b95-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d9b95-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d9b95-304">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-304">Int16</span></span>|
|<span data-ttu-id="d9b95-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d9b95-306">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-306">Int32</span></span>|
|<span data-ttu-id="d9b95-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="d9b95-308">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-308">Int32</span></span>|
|<span data-ttu-id="d9b95-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-309">IS_NULLABLE</span></span>|<span data-ttu-id="d9b95-310">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-310">String</span></span>|
|<span data-ttu-id="d9b95-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d9b95-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d9b95-312">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-312">String</span></span>|
|<span data-ttu-id="d9b95-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d9b95-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d9b95-314">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-314">String</span></span>|
|<span data-ttu-id="d9b95-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="d9b95-316">Byte</span><span class="sxs-lookup"><span data-stu-id="d9b95-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="d9b95-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="d9b95-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="d9b95-318">Microsoft SQL Server Oracle ODBC ドライバーは、共通のスキーマ コレクションに加えて次の特定のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d9b95-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="d9b95-319">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="d9b95-319">Tables</span></span>

- <span data-ttu-id="d9b95-320">列</span><span class="sxs-lookup"><span data-stu-id="d9b95-320">Columns</span></span>

- <span data-ttu-id="d9b95-321">手順</span><span class="sxs-lookup"><span data-stu-id="d9b95-321">Procedures</span></span>

- <span data-ttu-id="d9b95-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d9b95-322">ProcedureColumns</span></span>

- <span data-ttu-id="d9b95-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d9b95-323">ProcedureParameters</span></span>

- <span data-ttu-id="d9b95-324">Views</span><span class="sxs-lookup"><span data-stu-id="d9b95-324">Views</span></span>

- <span data-ttu-id="d9b95-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="d9b95-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="d9b95-326">Tables と Views</span><span class="sxs-lookup"><span data-stu-id="d9b95-326">Tables and Views</span></span>

|<span data-ttu-id="d9b95-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-327">ColumnName</span></span>|<span data-ttu-id="d9b95-328">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d9b95-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d9b95-330">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-330">String</span></span>|
|<span data-ttu-id="d9b95-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9b95-331">TABLE_OWNER</span></span>|<span data-ttu-id="d9b95-332">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-332">String</span></span>|
|<span data-ttu-id="d9b95-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-333">TABLE_NAME</span></span>|<span data-ttu-id="d9b95-334">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-334">String</span></span>|
|<span data-ttu-id="d9b95-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-335">TABLE_TYPE</span></span>|<span data-ttu-id="d9b95-336">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-336">String</span></span>|
|<span data-ttu-id="d9b95-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-337">REMARKS</span></span>|<span data-ttu-id="d9b95-338">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="d9b95-339">列</span><span class="sxs-lookup"><span data-stu-id="d9b95-339">Columns</span></span>

|<span data-ttu-id="d9b95-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-340">ColumnName</span></span>|<span data-ttu-id="d9b95-341">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d9b95-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d9b95-343">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-343">String</span></span>|
|<span data-ttu-id="d9b95-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9b95-344">TABLE_OWNER</span></span>|<span data-ttu-id="d9b95-345">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-345">String</span></span>|
|<span data-ttu-id="d9b95-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-346">TABLE_NAME</span></span>|<span data-ttu-id="d9b95-347">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-347">String</span></span>|
|<span data-ttu-id="d9b95-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-348">COLUMN_NAME</span></span>|<span data-ttu-id="d9b95-349">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-349">String</span></span>|
|<span data-ttu-id="d9b95-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-350">DATA_TYPE</span></span>|<span data-ttu-id="d9b95-351">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-351">Int16</span></span>|
|<span data-ttu-id="d9b95-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-352">TYPE_NAME</span></span>|<span data-ttu-id="d9b95-353">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-353">String</span></span>|
|<span data-ttu-id="d9b95-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d9b95-354">PRECISION</span></span>|<span data-ttu-id="d9b95-355">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-355">Int32</span></span>|
|<span data-ttu-id="d9b95-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-356">LENGTH</span></span>|<span data-ttu-id="d9b95-357">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-357">Int32</span></span>|
|<span data-ttu-id="d9b95-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="d9b95-358">SCALE</span></span>|<span data-ttu-id="d9b95-359">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-359">Int16</span></span>|
|<span data-ttu-id="d9b95-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="d9b95-360">RADIX</span></span>|<span data-ttu-id="d9b95-361">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-361">Int16</span></span>|
|<span data-ttu-id="d9b95-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-362">NULLABLE</span></span>|<span data-ttu-id="d9b95-363">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-363">Int16</span></span>|
|<span data-ttu-id="d9b95-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-364">REMARKS</span></span>|<span data-ttu-id="d9b95-365">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-365">String</span></span>|
|<span data-ttu-id="d9b95-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="d9b95-367">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="d9b95-368">手順</span><span class="sxs-lookup"><span data-stu-id="d9b95-368">Procedures</span></span>

|<span data-ttu-id="d9b95-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-369">ColumnName</span></span>|<span data-ttu-id="d9b95-370">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d9b95-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d9b95-372">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-372">String</span></span>|
|<span data-ttu-id="d9b95-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9b95-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d9b95-374">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-374">String</span></span>|
|<span data-ttu-id="d9b95-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="d9b95-376">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-376">String</span></span>|
|<span data-ttu-id="d9b95-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d9b95-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d9b95-378">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-378">Int16</span></span>|
|<span data-ttu-id="d9b95-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d9b95-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d9b95-380">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-380">Int16</span></span>|
|<span data-ttu-id="d9b95-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d9b95-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d9b95-382">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-382">Int16</span></span>|
|<span data-ttu-id="d9b95-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-383">REMARKS</span></span>|<span data-ttu-id="d9b95-384">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-384">String</span></span>|
|<span data-ttu-id="d9b95-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d9b95-386">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="d9b95-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d9b95-387">ProcedureColumns</span></span>

|<span data-ttu-id="d9b95-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-388">ColumnName</span></span>|<span data-ttu-id="d9b95-389">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d9b95-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d9b95-391">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-391">String</span></span>|
|<span data-ttu-id="d9b95-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9b95-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d9b95-393">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-393">String</span></span>|
|<span data-ttu-id="d9b95-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="d9b95-395">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-395">String</span></span>|
|<span data-ttu-id="d9b95-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-396">COLUMN_NAME</span></span>|<span data-ttu-id="d9b95-397">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-397">String</span></span>|
|<span data-ttu-id="d9b95-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-398">COLUMN_TYPE</span></span>|<span data-ttu-id="d9b95-399">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-399">Int16</span></span>|
|<span data-ttu-id="d9b95-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-400">DATA_TYPE</span></span>|<span data-ttu-id="d9b95-401">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-401">Int16</span></span>|
|<span data-ttu-id="d9b95-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-402">TYPE_NAME</span></span>|<span data-ttu-id="d9b95-403">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-403">String</span></span>|
|<span data-ttu-id="d9b95-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d9b95-404">PRECISION</span></span>|<span data-ttu-id="d9b95-405">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-405">Int32</span></span>|
|<span data-ttu-id="d9b95-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-406">LENGTH</span></span>|<span data-ttu-id="d9b95-407">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-407">Int32</span></span>|
|<span data-ttu-id="d9b95-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="d9b95-408">SCALE</span></span>|<span data-ttu-id="d9b95-409">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-409">Int16</span></span>|
|<span data-ttu-id="d9b95-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="d9b95-410">RADIX</span></span>|<span data-ttu-id="d9b95-411">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-411">Int16</span></span>|
|<span data-ttu-id="d9b95-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-412">NULLABLE</span></span>|<span data-ttu-id="d9b95-413">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-413">Int16</span></span>|
|<span data-ttu-id="d9b95-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-414">REMARKS</span></span>|<span data-ttu-id="d9b95-415">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-415">String</span></span>|
|<span data-ttu-id="d9b95-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d9b95-416">OVERLOAD</span></span>|<span data-ttu-id="d9b95-417">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-417">Int32</span></span>|
|<span data-ttu-id="d9b95-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="d9b95-419">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="d9b95-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="d9b95-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="d9b95-421">Microsoft Jet ODBC Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d9b95-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="d9b95-422">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="d9b95-422">Tables</span></span>

- <span data-ttu-id="d9b95-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="d9b95-423">Indexes</span></span>

- <span data-ttu-id="d9b95-424">列</span><span class="sxs-lookup"><span data-stu-id="d9b95-424">Columns</span></span>

- <span data-ttu-id="d9b95-425">手順</span><span class="sxs-lookup"><span data-stu-id="d9b95-425">Procedures</span></span>

- <span data-ttu-id="d9b95-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d9b95-426">ProcedureColumns</span></span>

- <span data-ttu-id="d9b95-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d9b95-427">ProcedureParameters</span></span>

- <span data-ttu-id="d9b95-428">Views</span><span class="sxs-lookup"><span data-stu-id="d9b95-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="d9b95-429">Tables と Views</span><span class="sxs-lookup"><span data-stu-id="d9b95-429">Tables and Views</span></span>

|<span data-ttu-id="d9b95-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-430">ColumnName</span></span>|<span data-ttu-id="d9b95-431">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d9b95-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d9b95-433">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-433">String</span></span>|
|<span data-ttu-id="d9b95-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9b95-434">TABLE_OWNER</span></span>|<span data-ttu-id="d9b95-435">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-435">String</span></span>|
|<span data-ttu-id="d9b95-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-436">TABLE_NAME</span></span>|<span data-ttu-id="d9b95-437">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-437">String</span></span>|
|<span data-ttu-id="d9b95-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-438">TABLE_TYPE</span></span>|<span data-ttu-id="d9b95-439">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-439">String</span></span>|
|<span data-ttu-id="d9b95-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-440">REMARKS</span></span>|<span data-ttu-id="d9b95-441">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="d9b95-442">列</span><span class="sxs-lookup"><span data-stu-id="d9b95-442">Columns</span></span>

|<span data-ttu-id="d9b95-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-443">ColumnName</span></span>|<span data-ttu-id="d9b95-444">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d9b95-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d9b95-446">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-446">String</span></span>|
|<span data-ttu-id="d9b95-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9b95-447">TABLE_OWNER</span></span>|<span data-ttu-id="d9b95-448">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-448">String</span></span>|
|<span data-ttu-id="d9b95-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-449">TABLE_NAME</span></span>|<span data-ttu-id="d9b95-450">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-450">String</span></span>|
|<span data-ttu-id="d9b95-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-451">COLUMN_NAME</span></span>|<span data-ttu-id="d9b95-452">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-452">String</span></span>|
|<span data-ttu-id="d9b95-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-453">DATA_TYPE</span></span>|<span data-ttu-id="d9b95-454">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-454">Int16</span></span>|
|<span data-ttu-id="d9b95-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-455">TYPE_NAME</span></span>|<span data-ttu-id="d9b95-456">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-456">String</span></span>|
|<span data-ttu-id="d9b95-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d9b95-457">PRECISION</span></span>|<span data-ttu-id="d9b95-458">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-458">Int32</span></span>|
|<span data-ttu-id="d9b95-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-459">LENGTH</span></span>|<span data-ttu-id="d9b95-460">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-460">Int32</span></span>|
|<span data-ttu-id="d9b95-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="d9b95-461">SCALE</span></span>|<span data-ttu-id="d9b95-462">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-462">Int16</span></span>|
|<span data-ttu-id="d9b95-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="d9b95-463">RADIX</span></span>|<span data-ttu-id="d9b95-464">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-464">Int16</span></span>|
|<span data-ttu-id="d9b95-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-465">NULLABLE</span></span>|<span data-ttu-id="d9b95-466">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-466">Int16</span></span>|
|<span data-ttu-id="d9b95-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-467">REMARKS</span></span>|<span data-ttu-id="d9b95-468">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-468">String</span></span>|
|<span data-ttu-id="d9b95-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="d9b95-470">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="d9b95-471">手順</span><span class="sxs-lookup"><span data-stu-id="d9b95-471">Procedures</span></span>

|<span data-ttu-id="d9b95-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-472">ColumnName</span></span>|<span data-ttu-id="d9b95-473">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d9b95-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d9b95-475">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-475">String</span></span>|
|<span data-ttu-id="d9b95-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9b95-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d9b95-477">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-477">String</span></span>|
|<span data-ttu-id="d9b95-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="d9b95-479">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-479">String</span></span>|
|<span data-ttu-id="d9b95-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d9b95-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d9b95-481">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-481">Int16</span></span>|
|<span data-ttu-id="d9b95-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d9b95-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d9b95-483">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-483">Int16</span></span>|
|<span data-ttu-id="d9b95-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d9b95-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d9b95-485">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-485">Int16</span></span>|
|<span data-ttu-id="d9b95-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-486">REMARKS</span></span>|<span data-ttu-id="d9b95-487">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-487">String</span></span>|
|<span data-ttu-id="d9b95-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d9b95-489">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="d9b95-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d9b95-490">ProcedureColumns</span></span>

|<span data-ttu-id="d9b95-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-491">ColumnName</span></span>|<span data-ttu-id="d9b95-492">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d9b95-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d9b95-494">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-494">String</span></span>|
|<span data-ttu-id="d9b95-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9b95-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d9b95-496">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-496">String</span></span>|
|<span data-ttu-id="d9b95-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="d9b95-498">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-498">String</span></span>|
|<span data-ttu-id="d9b95-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-499">COLUMN_NAME</span></span>|<span data-ttu-id="d9b95-500">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-500">String</span></span>|
|<span data-ttu-id="d9b95-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-501">COLUMN_TYPE</span></span>|<span data-ttu-id="d9b95-502">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-502">Int16</span></span>|
|<span data-ttu-id="d9b95-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-503">DATA_TYPE</span></span>|<span data-ttu-id="d9b95-504">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-504">Int16</span></span>|
|<span data-ttu-id="d9b95-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-505">TYPE_NAME</span></span>|<span data-ttu-id="d9b95-506">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-506">String</span></span>|
|<span data-ttu-id="d9b95-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d9b95-507">PRECISION</span></span>|<span data-ttu-id="d9b95-508">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-508">Int32</span></span>|
|<span data-ttu-id="d9b95-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-509">LENGTH</span></span>|<span data-ttu-id="d9b95-510">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-510">Int32</span></span>|
|<span data-ttu-id="d9b95-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="d9b95-511">SCALE</span></span>|<span data-ttu-id="d9b95-512">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-512">Int16</span></span>|
|<span data-ttu-id="d9b95-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="d9b95-513">RADIX</span></span>|<span data-ttu-id="d9b95-514">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-514">Int16</span></span>|
|<span data-ttu-id="d9b95-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-515">NULLABLE</span></span>|<span data-ttu-id="d9b95-516">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-516">Int16</span></span>|
|<span data-ttu-id="d9b95-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-517">REMARKS</span></span>|<span data-ttu-id="d9b95-518">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-518">String</span></span>|
|<span data-ttu-id="d9b95-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d9b95-519">OVERLOAD</span></span>|<span data-ttu-id="d9b95-520">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-520">Int32</span></span>|
|<span data-ttu-id="d9b95-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="d9b95-522">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="d9b95-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d9b95-523">ProcedureParameters</span></span>

|<span data-ttu-id="d9b95-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d9b95-524">ColumnName</span></span>|<span data-ttu-id="d9b95-525">DataType</span><span class="sxs-lookup"><span data-stu-id="d9b95-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d9b95-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d9b95-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="d9b95-527">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-527">String</span></span>|
|<span data-ttu-id="d9b95-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d9b95-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d9b95-529">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-529">String</span></span>|
|<span data-ttu-id="d9b95-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="d9b95-531">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-531">String</span></span>|
|<span data-ttu-id="d9b95-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-532">COLUMN_NAME</span></span>|<span data-ttu-id="d9b95-533">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-533">String</span></span>|
|<span data-ttu-id="d9b95-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-534">COLUMN_TYPE</span></span>|<span data-ttu-id="d9b95-535">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-535">Int16</span></span>|
|<span data-ttu-id="d9b95-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-536">DATA_TYPE</span></span>|<span data-ttu-id="d9b95-537">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-537">Int16</span></span>|
|<span data-ttu-id="d9b95-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9b95-538">TYPE_NAME</span></span>|<span data-ttu-id="d9b95-539">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-539">String</span></span>|
|<span data-ttu-id="d9b95-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d9b95-540">COLUMN_SIZE</span></span>|<span data-ttu-id="d9b95-541">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-541">Int32</span></span>|
|<span data-ttu-id="d9b95-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="d9b95-543">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-543">Int32</span></span>|
|<span data-ttu-id="d9b95-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d9b95-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d9b95-545">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-545">Int16</span></span>|
|<span data-ttu-id="d9b95-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d9b95-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d9b95-547">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-547">Int16</span></span>|
|<span data-ttu-id="d9b95-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-548">NULLABLE</span></span>|<span data-ttu-id="d9b95-549">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-549">Int16</span></span>|
|<span data-ttu-id="d9b95-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d9b95-550">REMARKS</span></span>|<span data-ttu-id="d9b95-551">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-551">String</span></span>|
|<span data-ttu-id="d9b95-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d9b95-552">COLUMN_DEF</span></span>|<span data-ttu-id="d9b95-553">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-553">String</span></span>|
|<span data-ttu-id="d9b95-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9b95-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d9b95-555">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-555">Int16</span></span>|
|<span data-ttu-id="d9b95-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d9b95-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d9b95-557">Int16</span><span class="sxs-lookup"><span data-stu-id="d9b95-557">Int16</span></span>|
|<span data-ttu-id="d9b95-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d9b95-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d9b95-559">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-559">Int32</span></span>|
|<span data-ttu-id="d9b95-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d9b95-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="d9b95-561">Int32</span><span class="sxs-lookup"><span data-stu-id="d9b95-561">Int32</span></span>|
|<span data-ttu-id="d9b95-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d9b95-562">IS_NULLABLE</span></span>|<span data-ttu-id="d9b95-563">String</span><span class="sxs-lookup"><span data-stu-id="d9b95-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="d9b95-564">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9b95-564">See also</span></span>

- [<span data-ttu-id="d9b95-565">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="d9b95-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
